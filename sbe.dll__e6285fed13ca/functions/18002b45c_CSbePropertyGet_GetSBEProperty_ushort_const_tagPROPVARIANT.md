# CSbePropertyGet::GetSBEProperty(ushort const *,tagPROPVARIANT *)

- ea: `0x18002b45c`
- end: `0x18002b6ac`
- name: `?GetSBEProperty@CSbePropertyGet@@QEAAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(CSbePropertyGet *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002a9e0`
- `0x18002b794`

## callees

- `0x180001c00`
- `0x18002b45c`
- `0x1800b6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b5aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b5aa`
- `KERNEL32!SystemTimeToFileTime` at `0x18002b617`
- `KERNEL32!SystemTimeToFileTime` at `0x18002b617`
- `KERNEL32!FileTimeToSystemTime` at `0x18002b5fc`
- `KERNEL32!FileTimeToSystemTime` at `0x18002b5fc`
- `ole32!CoTaskMemAlloc` at `0x18002b4ed`
- `ole32!CoTaskMemAlloc` at `0x18002b4ed`
- `ole32!CoTaskMemFree` at `0x18002b682`
- `ole32!CoTaskMemFree` at `0x18002b682`

## pseudocode

```c
__int64 __fastcall CSbePropertyGet::GetSBEProperty(
        CSbePropertyGet *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v4; // rcx
  unsigned int v7; // esi
  SIZE_T v8; // rcx
  BYTE *v9; // rax
  BYTE *v10; // rdi
  __int64 v11; // r14
  __int16 v12; // ax
  VARTYPE v13; // r14
  bool v14; // cf
  unsigned __int64 v15; // rcx
  _WORD v17[2]; // [rsp+40h] [rbp-30h] BYREF
  int v18; // [rsp+44h] [rbp-2Ch] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  v18 = 0;
  v17[0] = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v4 = *(_QWORD *)this;
  FileTime = 0;
  if ( !v4 )
    return (unsigned int)-1072887824;
  v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, int *, _QWORD, _WORD *))(*(_QWORD *)v4 + 40LL))(
         v4,
         a2,
         0,
         &v18,
         0,
         v17);
  if ( (v7 & 0x80000000) == 0 )
  {
    v8 = v17[0];
    if ( v18 == 1 )
      v8 = v17[0] + 2LL;
    v9 = (BYTE *)CoTaskMemAlloc(v8);
    v10 = v9;
    if ( v9 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, int *, BYTE *, _WORD *))(**(_QWORD **)this + 40LL))(
             *(_QWORD *)this,
             a2,
             0,
             &v18,
             v9,
             v17);
      if ( (v7 & 0x80000000) == 0 )
      {
        if ( v18 )
        {
          switch ( v18 )
          {
            case 1:
              v15 = (unsigned __int64)v17[0] >> 1;
              a3->hVal.QuadPart = (LONGLONG)v10;
              *(_WORD *)&v10[2 * v15] = 0;
              a3->vt = 31;
              return v7;
            case 2:
              a3->lVal = v17[0];
              a3->bstrblobVal.pData = v10;
              a3->vt = 65;
              return v7;
            case 3:
              v14 = *(_DWORD *)v10 != 0;
              a3->vt = 11;
              a3->iVal = -v14;
              break;
            case 4:
              v11 = 0;
              while ( (unsigned int)_o__wcsicmp(*((_QWORD *)&xmmword_1800D5BC0 + 5 * v11 + 3), a2) )
              {
                v11 = (unsigned int)(v11 + 1);
                if ( (unsigned int)v11 >= 0x3A )
                {
                  v12 = 21;
                  goto LABEL_23;
                }
              }
              v12 = *((_WORD *)&xmmword_1800D5BC0 + 20 * v11 + 10);
LABEL_23:
              v13 = 64;
              if ( v12 == 64 )
              {
                FileTime = *(struct _FILETIME *)v10;
                SystemTime = 0;
                if ( FileTimeToSystemTime((const FILETIME *)v10, &SystemTime) )
                {
                  SystemTime.wYear -= 1600;
                  SystemTimeToFileTime(&SystemTime, &FileTime);
                }
                a3->filetime = FileTime;
              }
              else
              {
                a3->hVal.QuadPart = *(_QWORD *)v10;
                v13 = 21;
              }
              a3->vt = v13;
              break;
            case 5:
              a3->iVal = *v10;
              a3->vt = 18;
              break;
            case 6:
              a3->hVal.QuadPart = (LONGLONG)v10;
              a3->vt = 72;
              return v7;
            default:
              v7 = -2147024809;
              break;
          }
        }
        else
        {
          a3->lVal = *(_DWORD *)v10;
          a3->vt = 19;
        }
      }
      CoTaskMemFree(v10);
      return v7;
    }
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18002b45c  push    rbp
0x18002b45e  push    rbx
0x18002b45f  push    rsi
0x18002b460  push    rdi
0x18002b461  push    r12
0x18002b463  push    r14
0x18002b465  push    r15
0x18002b467  mov     rbp, rsp
0x18002b46a  sub     rsp, 70h
0x18002b46e  mov     rax, cs:__security_cookie
0x18002b475  xor     rax, rsp
0x18002b478  mov     [rbp+var_10], rax
0x18002b47c  xor     eax, eax
0x18002b47e  mov     [rbp+var_2C], 0
0x18002b485  xorps   xmm0, xmm0
0x18002b488  mov     [rbp+var_30], ax
0x18002b48c  movups  xmmword ptr [r8], xmm0
0x18002b490  mov     [r8+10h], rax
0x18002b494  mov     r14, rcx
0x18002b497  mov     rcx, [rcx]
0x18002b49a  mov     rbx, r8
0x18002b49d  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18002b4a1  mov     r12, rdx
0x18002b4a4  test    rcx, rcx
0x18002b4a7  jz      loc_18002B68A
0x18002b4ad  mov     rax, [rcx]
0x18002b4b0  lea     rdx, [rbp+var_30]
0x18002b4b4  mov     [rsp+70h+var_48], rdx
0x18002b4b9  lea     r9, [rbp+var_2C]
0x18002b4bd  xor     r8d, r8d
0x18002b4c0  mov     [rsp+70h+var_50], 0
0x18002b4c9  mov     rdx, r12
0x18002b4cc  mov     rax, [rax+28h]
0x18002b4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4d5  mov     esi, eax
0x18002b4d7  test    eax, eax
0x18002b4d9  js      loc_18002B68F
0x18002b4df  cmp     [rbp+var_2C], 1
0x18002b4e3  movzx   ecx, [rbp+var_30]
0x18002b4e7  jnz     short loc_18002B4ED
0x18002b4e9  add     rcx, 2; cb
0x18002b4ed  call    cs:__imp_CoTaskMemAlloc
0x18002b4f3  mov     rdi, rax
0x18002b4f6  test    rax, rax
0x18002b4f9  jnz     short loc_18002B505
0x18002b4fb  mov     esi, 8007000Eh
0x18002b500  jmp     loc_18002B68F
0x18002b505  mov     rcx, [r14]
0x18002b508  lea     rdx, [rbp+var_30]
0x18002b50c  mov     [rsp+70h+var_48], rdx
0x18002b511  lea     r9, [rbp+var_2C]
0x18002b515  xor     r8d, r8d
0x18002b518  mov     [rsp+70h+var_50], rdi
0x18002b51d  mov     rdx, r12
0x18002b520  mov     rax, [rcx]
0x18002b523  mov     rax, [rax+28h]
0x18002b527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b52c  mov     esi, eax
0x18002b52e  test    eax, eax
0x18002b530  js      loc_18002B67F
0x18002b536  mov     ecx, [rbp+var_2C]
0x18002b539  test    ecx, ecx
0x18002b53b  jz      loc_18002B675
0x18002b541  sub     ecx, 1
0x18002b544  jz      loc_18002B65D
0x18002b54a  sub     ecx, 1
0x18002b54d  jz      loc_18002B64B
0x18002b553  sub     ecx, 1
0x18002b556  jz      loc_18002B639
0x18002b55c  sub     ecx, 1
0x18002b55f  jz      short loc_18002B594
0x18002b561  sub     ecx, 1
0x18002b564  jz      short loc_18002B583
0x18002b566  cmp     ecx, 1
0x18002b569  jz      short loc_18002B575
0x18002b56b  mov     esi, 80070057h
0x18002b570  jmp     loc_18002B67F
0x18002b575  mov     [rbx+8], rdi
0x18002b579  mov     word ptr [rbx], 48h ; 'H'
0x18002b57e  jmp     loc_18002B68F
0x18002b583  movzx   eax, byte ptr [rdi]
0x18002b586  mov     [rbx+8], ax
0x18002b58a  mov     word ptr [rbx], 12h
0x18002b58f  jmp     loc_18002B67F
0x18002b594  xor     r14d, r14d
0x18002b597  lea     rcx, xmmword_1800D5BC0
0x18002b59e  lea     r15, [r14+r14*4]
0x18002b5a2  mov     rdx, r12
0x18002b5a5  mov     rcx, [rcx+r15*8+18h]
0x18002b5aa  call    cs:__imp__o__wcsicmp
0x18002b5b0  mov     edx, 15h
0x18002b5b5  test    eax, eax
0x18002b5b7  jz      short loc_18002B5CE
0x18002b5b9  inc     r14d
0x18002b5bc  lea     rcx, xmmword_1800D5BC0
0x18002b5c3  cmp     r14d, 3Ah ; ':'
0x18002b5c7  jb      short loc_18002B59E
0x18002b5c9  movzx   eax, dx
0x18002b5cc  jmp     short loc_18002B5DB
0x18002b5ce  lea     rax, xmmword_1800D5BC0
0x18002b5d5  movzx   eax, word ptr [rax+r15*8+14h]
0x18002b5db  mov     rcx, [rdi]
0x18002b5de  mov     r14d, 40h ; '@'
0x18002b5e4  cmp     r14w, ax
0x18002b5e8  jnz     short loc_18002B62B
0x18002b5ea  mov     qword ptr [rbp+FileTime.dwLowDateTime], rcx
0x18002b5ee  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18002b5f2  xorps   xmm0, xmm0
0x18002b5f5  mov     rcx, rdi; lpFileTime
0x18002b5f8  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002b5fc  call    cs:__imp_FileTimeToSystemTime
0x18002b602  test    eax, eax
0x18002b604  jz      short loc_18002B61D
0x18002b606  mov     eax, 0F9C0h
0x18002b60b  lea     rdx, [rbp+FileTime]; lpFileTime
0x18002b60f  add     [rbp+SystemTime.wYear], ax
0x18002b613  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18002b617  call    cs:__imp_SystemTimeToFileTime
0x18002b61d  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18002b620  mov     [rbx+8], eax
0x18002b623  mov     eax, [rbp+FileTime.dwHighDateTime]
0x18002b626  mov     [rbx+0Ch], eax
0x18002b629  jmp     short loc_18002B633
0x18002b62b  mov     [rbx+8], rcx
0x18002b62f  movzx   r14d, dx
0x18002b633  mov     [rbx], r14w
0x18002b637  jmp     short loc_18002B67F
0x18002b639  mov     eax, [rdi]
0x18002b63b  neg     eax
0x18002b63d  mov     word ptr [rbx], 0Bh
0x18002b642  sbb     cx, cx
0x18002b645  mov     [rbx+8], cx
0x18002b649  jmp     short loc_18002B67F
0x18002b64b  movzx   eax, [rbp+var_30]
0x18002b64f  mov     [rbx+8], eax
0x18002b652  mov     [rbx+10h], rdi
0x18002b656  mov     word ptr [rbx], 41h ; 'A'
0x18002b65b  jmp     short loc_18002B68F
0x18002b65d  movzx   ecx, [rbp+var_30]
0x18002b661  shr     rcx, 1
0x18002b664  xor     eax, eax
0x18002b666  mov     [rbx+8], rdi
0x18002b66a  mov     [rdi+rcx*2], ax
0x18002b66e  mov     word ptr [rbx], 1Fh
0x18002b673  jmp     short loc_18002B68F
0x18002b675  mov     eax, [rdi]
0x18002b677  mov     [rbx+8], eax
0x18002b67a  mov     word ptr [rbx], 13h
0x18002b67f  mov     rcx, rdi; pv
0x18002b682  call    cs:__imp_CoTaskMemFree
0x18002b688  jmp     short loc_18002B68F
0x18002b68a  mov     esi, 0C00D07F0h
0x18002b68f  mov     eax, esi
0x18002b691  mov     rcx, [rbp+var_10]
0x18002b695  xor     rcx, rsp; StackCookie
0x18002b698  call    __security_check_cookie
0x18002b69d  add     rsp, 70h
0x18002b6a1  pop     r15
0x18002b6a3  pop     r14
0x18002b6a5  pop     r12
0x18002b6a7  pop     rdi
0x18002b6a8  pop     rsi
0x18002b6a9  pop     rbx
0x18002b6aa  pop     rbp
0x18002b6ab  retn
```
