# CNTFSSecurity::GetInheritSource(ulong,_ACL *,_INHERITED_FROMW * *)

- ea: `0x180006e20`
- end: `0x180007064`
- name: `?GetInheritSource@CNTFSSecurity@@UEAAJKPEAU_ACL@@PEAPEAU_INHERITED_FROMW@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(LPWSTR *this, SECURITY_INFORMATION, struct _ACL *, struct _INHERITED_FROMW **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006e20`
- `0x180007ce0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000703b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000703b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007044`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f7a`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180006e54`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180006e54`
- `ADVAPI32!FreeInheritedFromArray` at `0x180007023`
- `ADVAPI32!FreeInheritedFromArray` at `0x180007023`
- `ADVAPI32!GetInheritanceSourceW` at `0x180006eca`
- `ADVAPI32!GetInheritanceSourceW` at `0x180006eca`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GetInheritSource(
        LPWSTR *this,
        SECURITY_INFORMATION a2,
        struct _ACL *a3,
        struct _INHERITED_FROMW **a4)
{
  signed int v8; // ebx
  struct _INHERITED_FROMW *pInheritArray; // r14
  signed int InheritanceSourceW; // eax
  __int64 AceCount; // r9
  struct _INHERITED_FROMW *v12; // rdi
  unsigned __int64 v13; // rbp
  unsigned int i; // r8d
  LPWSTR AncestorName; // rcx
  __int64 v16; // rdx
  struct _INHERITED_FROMW *v17; // rax
  WORD v18; // cx
  unsigned int v19; // r15d
  unsigned __int16 *v20; // r10
  DWORD GuidCount; // [rsp+28h] [rbp-80h]
  unsigned __int16 *v23; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v24; // [rsp+C0h] [rbp+18h] BYREF

  if ( a3 && a4 )
  {
    if ( IsValidAcl(a3) )
    {
      pInheritArray = (struct _INHERITED_FROMW *)LocalAlloc(0x40u, 16LL * a3->AceCount);
      if ( pInheritArray )
      {
        InheritanceSourceW = GetInheritanceSourceW(
                               this[4],
                               SE_FILE_OBJECT,
                               a2,
                               (_DWORD)this[5] & 4,
                               0,
                               0,
                               a3,
                               0,
                               &STANDARD_FILE_MAP,
                               pInheritArray);
        v8 = InheritanceSourceW;
        if ( InheritanceSourceW > 0 )
          v8 = (unsigned __int16)InheritanceSourceW | 0x80070000;
        if ( v8 >= 0 )
        {
          AceCount = a3->AceCount;
          v12 = 0;
          v24 = 0;
          v13 = 0;
          for ( i = 0; i < (unsigned int)AceCount; ++i )
          {
            AncestorName = pInheritArray[i].AncestorName;
            if ( AncestorName )
            {
              v16 = 0x7FFFFFFF;
              do
              {
                if ( !*AncestorName )
                  break;
                ++AncestorName;
                --v16;
              }
              while ( v16 );
              v8 = v16 == 0 ? 0x80070057 : 0;
              if ( !v16 )
                goto LABEL_25;
              v13 += ((2 * (0x7FFFFFFF - v16)) & -(__int64)(v16 != 0)) + 2;
              v24 = v13;
            }
          }
          v17 = (struct _INHERITED_FROMW *)LocalAlloc(0x40u, v13 + 16 * AceCount);
          v12 = v17;
          if ( v17 )
          {
            v18 = a3->AceCount;
            v19 = 0;
            v23 = 0;
            v20 = (unsigned __int16 *)&v17[v18];
            if ( v18 )
            {
              do
              {
                v12[v19].GenerationGap = pInheritArray[v19].GenerationGap;
                if ( pInheritArray[v19].AncestorName )
                {
                  v12[v19].AncestorName = v20;
                  v8 = StringCbCopyExW(v20, v13, pInheritArray[v19].AncestorName, &v23, &v24, GuidCount);
                  if ( v8 < 0 )
                    break;
                  v13 = v24 - 2;
                  v24 -= 2LL;
                  v20 = v23 + 1;
                }
                ++v19;
              }
              while ( v19 < a3->AceCount );
            }
          }
          else
          {
            v8 = -2147024882;
          }
LABEL_25:
          FreeInheritedFromArray(pInheritArray, a3->AceCount, 0);
          if ( v8 < 0 )
          {
            if ( v12 )
              LocalFree(v12);
          }
          else
          {
            *a4 = v12;
          }
        }
        LocalFree(pInheritArray);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006e20  push    rbx
0x180006e22  push    rbp
0x180006e23  push    rsi
0x180006e24  push    rdi
0x180006e25  push    r12
0x180006e27  push    r13
0x180006e29  push    r14
0x180006e2b  push    r15
0x180006e2d  sub     rsp, 68h
0x180006e31  xor     r13d, r13d
0x180006e34  mov     r12, r9
0x180006e37  mov     rsi, r8
0x180006e3a  mov     edi, edx
0x180006e3c  mov     rbx, rcx
0x180006e3f  test    r8, r8
0x180006e42  jz      loc_18000704C
0x180006e48  test    r9, r9
0x180006e4b  jz      loc_18000704C
0x180006e51  mov     rcx, r8; pAcl
0x180006e54  call    cs:__imp_IsValidAcl
0x180006e5a  test    eax, eax
0x180006e5c  jnz     short loc_180006E68
0x180006e5e  mov     ebx, 80070057h
0x180006e63  jmp     loc_180007051
0x180006e68  movzx   edx, word ptr [rsi+4]
0x180006e6c  mov     r15d, 40h ; '@'
0x180006e72  shl     rdx, 4; uBytes
0x180006e76  mov     ecx, r15d; uFlags
0x180006e79  call    cs:__imp_LocalAlloc
0x180006e7f  mov     r14, rax
0x180006e82  test    rax, rax
0x180006e85  jnz     short loc_180006E91
0x180006e87  mov     ebx, 8007000Eh
0x180006e8c  jmp     loc_180007051
0x180006e91  mov     r9d, [rbx+28h]
0x180006e95  lea     rax, ?STANDARD_FILE_MAP@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING STANDARD_FILE_MAP
0x180006e9c  mov     rcx, [rbx+20h]; pObjectName
0x180006ea0  and     r9d, 4; Container
0x180006ea4  mov     [rsp+0A8h+pInheritArray], r14; pInheritArray
0x180006ea9  mov     r8d, edi; SecurityInfo
0x180006eac  mov     [rsp+0A8h+pGenericMapping], rax; pGenericMapping
0x180006eb1  mov     edx, 1; ObjectType
0x180006eb6  mov     [rsp+0A8h+pfnArray], r13; pfnArray
0x180006ebb  mov     [rsp+0A8h+pAcl], rsi; pAcl
0x180006ec0  mov     [rsp+0A8h+GuidCount], r13d; unsigned int
0x180006ec5  mov     [rsp+0A8h+pObjectClassGuids], r13; pObjectClassGuids
0x180006eca  call    cs:__imp_GetInheritanceSourceW
0x180006ed0  mov     ebx, eax
0x180006ed2  test    eax, eax
0x180006ed4  jle     short loc_180006EDF
0x180006ed6  movzx   ebx, ax
0x180006ed9  or      ebx, 80070000h
0x180006edf  test    ebx, ebx
0x180006ee1  js      loc_180007041
0x180006ee7  movzx   r9d, word ptr [rsi+4]
0x180006eec  mov     rdi, r13
0x180006eef  mov     [rsp+0A8h+arg_10], r13
0x180006ef7  mov     rbp, r13
0x180006efa  mov     r8d, r13d
0x180006efd  test    r9d, r9d
0x180006f00  jz      short loc_180006F6D
0x180006f02  mov     r10d, 7FFFFFFFh
0x180006f08  mov     eax, r8d
0x180006f0b  add     rax, rax
0x180006f0e  mov     rcx, [r14+rax*8+8]
0x180006f13  test    rcx, rcx
0x180006f16  jz      short loc_180006F65
0x180006f18  mov     rdx, r10
0x180006f1b  cmp     [rcx], r13w
0x180006f1f  jz      short loc_180006F2B
0x180006f21  add     rcx, 2
0x180006f25  sub     rdx, 1
0x180006f29  jnz     short loc_180006F1B
0x180006f2b  mov     rax, rdx
0x180006f2e  neg     rax
0x180006f31  sbb     ebx, ebx
0x180006f33  not     ebx
0x180006f35  and     ebx, 80070057h
0x180006f3b  test    rdx, rdx
0x180006f3e  jz      loc_180007019
0x180006f44  mov     rcx, r10
0x180006f47  sub     rcx, rdx
0x180006f4a  add     rcx, rcx
0x180006f4d  neg     rdx
0x180006f50  sbb     rax, rax
0x180006f53  add     rbp, 2
0x180006f57  and     rax, rcx
0x180006f5a  add     rbp, rax
0x180006f5d  mov     [rsp+0A8h+arg_10], rbp
0x180006f65  inc     r8d
0x180006f68  cmp     r8d, r9d
0x180006f6b  jb      short loc_180006F08
0x180006f6d  mov     rdx, r9
0x180006f70  mov     ecx, r15d; uFlags
0x180006f73  shl     rdx, 4
0x180006f77  add     rdx, rbp; uBytes
0x180006f7a  call    cs:__imp_LocalAlloc
0x180006f80  mov     rdi, rax
0x180006f83  test    rax, rax
0x180006f86  jnz     short loc_180006F92
0x180006f88  mov     ebx, 8007000Eh
0x180006f8d  jmp     loc_180007019
0x180006f92  movzx   ecx, word ptr [rsi+4]
0x180006f96  mov     r15d, r13d
0x180006f99  mov     r10d, ecx
0x180006f9c  mov     [rsp+0A8h+var_58], r13
0x180006fa1  shl     r10, 4
0x180006fa5  add     r10, rdi
0x180006fa8  cmp     r13w, cx
0x180006fac  jnb     short loc_180007019
0x180006fae  mov     r8d, r15d
0x180006fb1  add     r8, r8
0x180006fb4  mov     eax, [r14+r8*8]
0x180006fb8  mov     [rdi+r8*8], eax
0x180006fbc  cmp     [r14+r8*8+8], r13
0x180006fc1  jz      short loc_18000700D
0x180006fc3  mov     [rdi+r8*8+8], r10
0x180006fc8  lea     rax, [rsp+0A8h+arg_10]
0x180006fd0  mov     r8, [r14+r8*8+8]; unsigned __int16 *
0x180006fd5  lea     r9, [rsp+0A8h+var_58]; unsigned __int16 **
0x180006fda  mov     rdx, rbp; unsigned __int64
0x180006fdd  mov     [rsp+0A8h+pObjectClassGuids], rax; unsigned __int64 *
0x180006fe2  mov     rcx, r10; unsigned __int16 *
0x180006fe5  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180006fea  mov     ebx, eax
0x180006fec  test    eax, eax
0x180006fee  js      short loc_180007019
0x180006ff0  mov     rbp, [rsp+0A8h+arg_10]
0x180006ff8  mov     r10, [rsp+0A8h+var_58]
0x180006ffd  sub     rbp, 2
0x180007001  mov     [rsp+0A8h+arg_10], rbp
0x180007009  add     r10, 2
0x18000700d  movzx   ecx, word ptr [rsi+4]
0x180007011  inc     r15d
0x180007014  cmp     r15d, ecx
0x180007017  jb      short loc_180006FAE
0x180007019  movzx   edx, word ptr [rsi+4]; AceCnt
0x18000701d  xor     r8d, r8d; pfnArray
0x180007020  mov     rcx, r14; pInheritArray
0x180007023  call    cs:__imp_FreeInheritedFromArray
0x180007029  test    ebx, ebx
0x18000702b  js      short loc_180007033
0x18000702d  mov     [r12], rdi
0x180007031  jmp     short loc_180007041
0x180007033  test    rdi, rdi
0x180007036  jz      short loc_180007041
0x180007038  mov     rcx, rdi; hMem
0x18000703b  call    cs:__imp_LocalFree
0x180007041  mov     rcx, r14; hMem
0x180007044  call    cs:__imp_LocalFree
0x18000704a  jmp     short loc_180007051
0x18000704c  mov     ebx, 80004003h
0x180007051  mov     eax, ebx
0x180007053  add     rsp, 68h
0x180007057  pop     r15
0x180007059  pop     r14
0x18000705b  pop     r13
0x18000705d  pop     r12
0x18000705f  pop     rdi
0x180007060  pop     rsi
0x180007061  pop     rbp
0x180007062  pop     rbx
0x180007063  retn
```
