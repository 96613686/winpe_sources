# WinStationEnumerateExW

- ea: `0x180012b40`
- end: `0x180012e37`
- name: `WinStationEnumerateExW`
- size: `759`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800083fc`
- `0x180008494`
- `0x180012b40`
- `0x180012e40`
- `0x180014eb4`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012be5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012be5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012c2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012c2f`

## string_xrefs

- `0x180012b92`: `Failed to open binding`
- `0x180012bc1`: `Enum->Open failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationEnumerateExW(void *a1, _QWORD *a2, _DWORD *a3)
{
  char v5; // bl
  void *v6; // rax
  unsigned int v7; // edx
  int EnumResult; // edi
  DWORD v9; // ecx
  unsigned int v10; // eax
  size_t v11; // rsi
  _BYTE *v12; // rax
  _BYTE *v13; // rdi
  unsigned int v14; // r8d
  unsigned __int64 i; // r9
  __int64 v16; // r11
  __int64 v17; // rdx
  __int64 v18; // r10
  __int64 v19; // rcx
  _WORD *v20; // rsi
  _WORD *v21; // rax
  _WORD *v22; // rcx
  _OWORD *v23; // rax
  __int64 v24; // rdx
  _OWORD *v25; // rcx
  __int128 v26; // xmm1
  unsigned __int16 v28[8]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+78h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+50h] BYREF
  __int64 v31; // [rsp+88h] [rbp+58h] BYREF

  *a2 = 0;
  *a3 = 0;
  hMem = 0;
  v29 = 0;
  v5 = 0;
  v31 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v28, a1, 0);
  if ( !CSmartPublicBinding::operator void *(v28) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_31;
  }
  v6 = (void *)CSmartPublicBinding::operator void *(v28);
  EnumResult = CEnum::Open((CEnum *)&v31, v6);
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", (unsigned int)EnumResult, "WinStationEnumerateExW");
LABEL_5:
    v9 = ConvertHRESULT2WIN32(EnumResult);
LABEL_6:
    SetLastError(v9);
    goto LABEL_31;
  }
  EnumResult = CEnum::GetEnumResultEx((CEnum *)&v31, v7, (struct _SESSIONENUM_EX **)&hMem, &v29);
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "GetEnumResultEx failed: 0x%x in %s", (unsigned int)EnumResult, "WinStationEnumerateExW");
    goto LABEL_5;
  }
  v10 = 1112 * v29;
  if ( 1112 * v29 )
  {
    v11 = v10;
    v12 = LocalAlloc(0, v10);
    v13 = v12;
    if ( !v12 )
    {
      v9 = 8;
      goto LABEL_6;
    }
    memset_0(v12, 0, v11);
    v14 = 0;
    v5 = 1;
    for ( i = v11 / 0x458; v14 < (unsigned int)i; ++v14 )
    {
      if ( v14 >= v29 )
        break;
      v16 = 33;
      v17 = 120LL * v14;
      v18 = 1112LL * v14;
      *(_DWORD *)&v13[v18] = *(_DWORD *)((char *)hMem + v17 + 8);
      *(_DWORD *)&v13[v18 + 4] = *(_DWORD *)((char *)hMem + v17 + 12);
      v19 = 2147483646;
      v20 = (char *)hMem + v17 + 16;
      v21 = &v13[v18 + 32];
      do
      {
        if ( !v19 )
          break;
        if ( !*v20 )
          break;
        *v21++ = *v20++;
        --v19;
        --v16;
      }
      while ( v16 );
      v22 = v21 - 1;
      if ( v16 )
        v22 = v21;
      *v22 = 0;
      if ( *(_DWORD *)((char *)hMem + v17) >= 2u )
      {
        *(_DWORD *)&v13[v18 + 8] = *(_DWORD *)((char *)hMem + v17 + 84);
        *(_OWORD *)&v13[v18 + 16] = *(_OWORD *)((char *)hMem + v17 + 92);
        v13[v18 + 12] = *((_BYTE *)hMem + v17 + 88);
      }
      if ( *(_DWORD *)((char *)hMem + v17) == 3 )
      {
        v23 = *(_OWORD **)((char *)hMem + v17 + 112);
        if ( v23 )
        {
          if ( *(_DWORD *)((char *)hMem + v17 + 108) >= 0x3F4u )
          {
            v24 = 7;
            v25 = &v13[v18 + 100];
            do
            {
              *v25 = *v23;
              v25[1] = v23[1];
              v25[2] = v23[2];
              v25[3] = v23[3];
              v25[4] = v23[4];
              v25[5] = v23[5];
              v25[6] = v23[6];
              v26 = v23[7];
              v23 += 8;
              v25[7] = v26;
              v25 += 8;
              --v24;
            }
            while ( v24 );
            *v25 = *v23;
            v25[1] = v23[1];
            v25[2] = v23[2];
            v25[3] = v23[3];
            v25[4] = v23[4];
            v25[5] = v23[5];
            v25[6] = v23[6];
            *((_DWORD *)v25 + 28) = *((_DWORD *)v23 + 28);
          }
        }
      }
    }
    *a2 = v13;
    *a3 = i;
  }
  else
  {
    v5 = 1;
  }
LABEL_31:
  if ( hMem )
    CEnum::FreeEnumResultEx(hMem, v29);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v28);
  CEnum::~CEnum((CEnum *)&v31);
  return v5;
}

```

## disassembly

```asm
0x180012b40  mov     [rsp-38h+arg_0], rbx
0x180012b45  push    rbp
0x180012b46  push    rsi
0x180012b47  push    rdi
0x180012b48  push    r12
0x180012b4a  push    r13
0x180012b4c  push    r14
0x180012b4e  push    r15
0x180012b50  mov     rbp, rsp
0x180012b53  sub     rsp, 30h
0x180012b57  xor     r13d, r13d
0x180012b5a  mov     r12, rdx
0x180012b5d  mov     [rdx], r13
0x180012b60  mov     r15, r8
0x180012b63  mov     [r8], r13d
0x180012b66  mov     rdx, rcx; void *
0x180012b69  xor     r8d, r8d; int
0x180012b6c  mov     [rbp+hMem], r13
0x180012b70  lea     rcx, [rbp+var_10]; this
0x180012b74  mov     [rbp+arg_8], r13d
0x180012b78  mov     bl, r13b
0x180012b7b  mov     [rbp+arg_18], r13
0x180012b7f  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180012b84  lea     rcx, [rbp+var_10]; unsigned __int16 *
0x180012b88  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180012b8d  test    rax, rax
0x180012b90  jnz     short loc_180012BA6
0x180012b92  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180012b99  lea     ecx, [rax+8]; int
0x180012b9c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012ba1  jmp     loc_180012DFC
0x180012ba6  lea     rcx, [rbp+var_10]; unsigned __int16 *
0x180012baa  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180012baf  mov     rdx, rax; void *
0x180012bb2  lea     rcx, [rbp+arg_18]; this
0x180012bb6  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x180012bbb  mov     edi, eax
0x180012bbd  test    eax, eax
0x180012bbf  jns     short loc_180012BF6
0x180012bc1  lea     rdx, aEnumOpenFailed; "Enum->Open failed: 0x%x in %s"
0x180012bc8  mov     r8d, edi
0x180012bcb  lea     r9, aWinstationenum_9; "WinStationEnumerateExW"
0x180012bd2  mov     ecx, 8; int
0x180012bd7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012bdc  mov     ecx, edi; int
0x180012bde  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180012be3  mov     ecx, eax; dwErrCode
0x180012be5  call    cs:__imp_SetLastError
0x180012bec  nop     dword ptr [rax+rax+00h]
0x180012bf1  jmp     loc_180012DFC
0x180012bf6  lea     r9, [rbp+arg_8]; unsigned int *
0x180012bfa  lea     r8, [rbp+hMem]; struct _SESSIONENUM_EX **
0x180012bfe  lea     rcx, [rbp+arg_18]; this
0x180012c02  call    ?GetEnumResultEx@CEnum@@QEAAJKPEAPEAU_SESSIONENUM_EX@@PEAK@Z; CEnum::GetEnumResultEx(ulong,_SESSIONENUM_EX * *,ulong *)
0x180012c07  mov     edi, eax
0x180012c09  test    eax, eax
0x180012c0b  jns     short loc_180012C16
0x180012c0d  lea     rdx, aGetenumresulte; "GetEnumResultEx failed: 0x%x in %s"
0x180012c14  jmp     short loc_180012BC8
0x180012c16  imul    eax, [rbp+arg_8], 458h
0x180012c1d  test    eax, eax
0x180012c1f  jnz     short loc_180012C29
0x180012c21  lea     ebx, [rax+1]
0x180012c24  jmp     loc_180012DFC
0x180012c29  mov     edx, eax; uBytes
0x180012c2b  xor     ecx, ecx; uFlags
0x180012c2d  mov     esi, eax
0x180012c2f  call    cs:__imp_LocalAlloc
0x180012c36  nop     dword ptr [rax+rax+00h]
0x180012c3b  mov     rdi, rax
0x180012c3e  test    rax, rax
0x180012c41  jnz     short loc_180012C48
0x180012c43  lea     ecx, [rax+8]
0x180012c46  jmp     short loc_180012BE5
0x180012c48  mov     r8, rsi; Size
0x180012c4b  xor     edx, edx; Val
0x180012c4d  mov     rcx, rdi; void *
0x180012c50  call    memset_0
0x180012c55  mov     rax, 3AEF6CA970586723h
0x180012c5f  mov     r8d, r13d
0x180012c62  mul     rsi
0x180012c65  mov     ebx, 1
0x180012c6a  mov     r9, rdx
0x180012c6d  shr     r9, 8
0x180012c71  test    r9d, r9d
0x180012c74  jz      loc_180012DF5
0x180012c7a  cmp     r8d, [rbp+arg_8]
0x180012c7e  jnb     loc_180012DF5
0x180012c84  mov     eax, r8d
0x180012c87  mov     r11d, 21h ; '!'
0x180012c8d  imul    rdx, rax, 78h ; 'x'
0x180012c91  imul    r10, rax, 458h
0x180012c98  mov     rax, [rbp+hMem]
0x180012c9c  mov     ecx, [rdx+rax+8]
0x180012ca0  mov     [r10+rdi], ecx
0x180012ca4  mov     rax, [rbp+hMem]
0x180012ca8  mov     ecx, [rdx+rax+0Ch]
0x180012cac  lea     rax, [rdi+20h]
0x180012cb0  mov     [r10+rdi+4], ecx
0x180012cb5  mov     ecx, 7FFFFFFEh
0x180012cba  mov     rsi, [rbp+hMem]
0x180012cbe  add     rsi, 10h
0x180012cc2  add     rsi, rdx
0x180012cc5  add     rax, r10
0x180012cc8  test    rcx, rcx
0x180012ccb  jz      short loc_180012CEB
0x180012ccd  movzx   r14d, word ptr [rsi]
0x180012cd1  test    r14w, r14w
0x180012cd5  jz      short loc_180012CEB
0x180012cd7  mov     [rax], r14w
0x180012cdb  add     rsi, 2
0x180012cdf  add     rax, 2
0x180012ce3  sub     rcx, rbx
0x180012ce6  sub     r11, rbx
0x180012ce9  jnz     short loc_180012CC8
0x180012ceb  test    r11, r11
0x180012cee  lea     rcx, [rax-2]
0x180012cf2  cmovnz  rcx, rax
0x180012cf6  mov     [rcx], r13w
0x180012cfa  mov     rax, [rbp+hMem]
0x180012cfe  cmp     dword ptr [rdx+rax], 2
0x180012d02  jb      short loc_180012D2A
0x180012d04  mov     eax, [rdx+rax+54h]
0x180012d08  mov     [r10+rdi+8], eax
0x180012d0d  mov     rax, [rbp+hMem]
0x180012d11  movups  xmm0, xmmword ptr [rdx+rax+5Ch]
0x180012d16  movdqu  xmmword ptr [r10+rdi+10h], xmm0
0x180012d1d  mov     rax, [rbp+hMem]
0x180012d21  mov     cl, [rdx+rax+58h]
0x180012d25  mov     [r10+rdi+0Ch], cl
0x180012d2a  mov     rcx, [rbp+hMem]
0x180012d2e  cmp     dword ptr [rdx+rcx], 3
0x180012d32  jnz     loc_180012DE9
0x180012d38  mov     rax, [rdx+rcx+70h]
0x180012d3d  test    rax, rax
0x180012d40  jz      loc_180012DE9
0x180012d46  cmp     dword ptr [rdx+rcx+6Ch], 3F4h
0x180012d4e  jb      loc_180012DE9
0x180012d54  mov     edx, 7
0x180012d59  lea     rcx, [rdi+64h]
0x180012d5d  add     rcx, r10
0x180012d60  lea     r14d, [rdx+79h]
0x180012d64  movups  xmm0, xmmword ptr [rax]
0x180012d67  movups  xmmword ptr [rcx], xmm0
0x180012d6a  movups  xmm1, xmmword ptr [rax+10h]
0x180012d6e  movups  xmmword ptr [rcx+10h], xmm1
0x180012d72  movups  xmm0, xmmword ptr [rax+20h]
0x180012d76  movups  xmmword ptr [rcx+20h], xmm0
0x180012d7a  movups  xmm1, xmmword ptr [rax+30h]
0x180012d7e  movups  xmmword ptr [rcx+30h], xmm1
0x180012d82  movups  xmm0, xmmword ptr [rax+40h]
0x180012d86  movups  xmmword ptr [rcx+40h], xmm0
0x180012d8a  movups  xmm1, xmmword ptr [rax+50h]
0x180012d8e  movups  xmmword ptr [rcx+50h], xmm1
0x180012d92  movups  xmm0, xmmword ptr [rax+60h]
0x180012d96  movups  xmmword ptr [rcx+60h], xmm0
0x180012d9a  movups  xmm1, xmmword ptr [rax+70h]
0x180012d9e  add     rax, r14
0x180012da1  movups  xmmword ptr [rcx+70h], xmm1
0x180012da5  add     rcx, r14
0x180012da8  sub     rdx, rbx
0x180012dab  jnz     short loc_180012D64
0x180012dad  movups  xmm0, xmmword ptr [rax]
0x180012db0  movups  xmmword ptr [rcx], xmm0
0x180012db3  movups  xmm1, xmmword ptr [rax+10h]
0x180012db7  movups  xmmword ptr [rcx+10h], xmm1
0x180012dbb  movups  xmm0, xmmword ptr [rax+20h]
0x180012dbf  movups  xmmword ptr [rcx+20h], xmm0
0x180012dc3  movups  xmm1, xmmword ptr [rax+30h]
0x180012dc7  movups  xmmword ptr [rcx+30h], xmm1
0x180012dcb  movups  xmm0, xmmword ptr [rax+40h]
0x180012dcf  movups  xmmword ptr [rcx+40h], xmm0
0x180012dd3  movups  xmm1, xmmword ptr [rax+50h]
0x180012dd7  movups  xmmword ptr [rcx+50h], xmm1
0x180012ddb  movups  xmm0, xmmword ptr [rax+60h]
0x180012ddf  movups  xmmword ptr [rcx+60h], xmm0
0x180012de3  mov     eax, [rax+70h]
0x180012de6  mov     [rcx+70h], eax
0x180012de9  add     r8d, ebx
0x180012dec  cmp     r8d, r9d
0x180012def  jb      loc_180012C7A
0x180012df5  mov     [r12], rdi
0x180012df9  mov     [r15], r9d
0x180012dfc  mov     rcx, [rbp+hMem]; hMem
0x180012e00  test    rcx, rcx
0x180012e03  jz      short loc_180012E0D
0x180012e05  mov     edx, [rbp+arg_8]; unsigned int
0x180012e08  call    ?FreeEnumResultEx@CEnum@@SAJPEAU_SESSIONENUM_EX@@K@Z; CEnum::FreeEnumResultEx(_SESSIONENUM_EX *,ulong)
0x180012e0d  lea     rcx, [rbp+var_10]; this
0x180012e11  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180012e16  lea     rcx, [rbp+arg_18]; this
0x180012e1a  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x180012e1f  mov     al, bl
0x180012e21  mov     rbx, [rsp+30h+arg_0]
0x180012e26  add     rsp, 30h
0x180012e2a  pop     r15
0x180012e2c  pop     r14
0x180012e2e  pop     r13
0x180012e30  pop     r12
0x180012e32  pop     rdi
0x180012e33  pop     rsi
0x180012e34  pop     rbp
0x180012e35  retn
```
