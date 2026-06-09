# QueryTransientObjectSecurityDescriptor

- ea: `0x180012100`
- end: `0x18001227d`
- name: `QueryTransientObjectSecurityDescriptor`
- size: `381`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180037900`
- `0x180037aa0`
- `0x180037b90`
- `0x180037c60`

## callees

- `0x180011e4c`
- `0x180012100`
- `0x180012290`
- `0x180012300`
- `0x1800125c8`
- `0x1800237d8`
- `0x1800238ec`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x1800121da`
- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x1800121da`
- `ntdll!RtlCopySecurityDescriptor` at `0x180012235`
- `ntdll!RtlCopySecurityDescriptor` at `0x180012235`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001224d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001224d`

## pseudocode

```c
__int64 __fastcall QueryTransientObjectSecurityDescriptor(__int64 a1, __int64 a2, PSECURITY_DESCRIPTOR *a3)
{
  _WORD *v3; // rsi
  __int64 v4; // rdi
  int NormalizedObjectPath; // eax
  unsigned int v7; // ebx
  int v8; // eax
  void *v9; // rax
  void *v10; // r14
  __int64 v11; // r14
  unsigned __int64 v12; // rbx
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  int SystemCapabilitySecurityDescriptor; // eax
  _WORD *v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 SubStr; // [rsp+78h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR pSourceSecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  v3 = 0;
  v4 = 0;
  v17 = 0;
  SubStr = 0;
  pSourceSecurityDescriptor = 0;
  if ( !a2 || !a3 )
  {
    v7 = -1073741811;
    goto LABEL_19;
  }
  NormalizedObjectPath = GetNormalizedObjectPath(a1, a2, &v17);
  v3 = v17;
  v7 = NormalizedObjectPath;
  if ( NormalizedObjectPath >= 0 )
  {
    v8 = QuerySecurityDescriptorValue(v17, &SubStr);
    v4 = SubStr;
    v7 = v8;
    if ( v8 >= 0 )
    {
      if ( *(_DWORD *)(SubStr + 4) == 3 )
      {
        v9 = (void *)AccessHlprAlloc(*(unsigned int *)(SubStr + 8));
        v10 = v9;
        if ( v9 )
        {
          memcpy_0(v9, (const void *)(v4 + 12), *(unsigned int *)(v4 + 8));
          *a3 = v10;
        }
        else
        {
          v7 = -1073741801;
        }
        goto LABEL_19;
      }
      if ( *(_DWORD *)(SubStr + 4) != 1 || !*(_DWORD *)(SubStr + 8) )
      {
LABEL_11:
        v7 = -1073739509;
        goto LABEL_19;
      }
      v11 = SubStr + 12;
      v12 = (unsigned __int64)*(unsigned int *)(SubStr + 8) >> 1;
      wcscpy((wchar_t *)&SubStr, L"}");
      v13 = (const wchar_t *)(v4 + 12);
      if ( *(_WORD *)(v4 + 12) == 123 )
      {
        v14 = wcsstr(v13, (const wchar_t *)&SubStr);
        if ( !v14 )
          goto LABEL_11;
        *v14 = 0;
        SystemCapabilitySecurityDescriptor = CreateSystemCapabilitySecurityDescriptor(
                                               (int)v4 + 14,
                                               ((__int64)v14 - v11) >> 1,
                                               (int)v14 + 2,
                                               v12 - ((((__int64)v14 - v11) >> 1) - 1) - 2,
                                               (__int64)&pSourceSecurityDescriptor);
      }
      else
      {
        SystemCapabilitySecurityDescriptor = CreatePerUserSecurityDescriptor((__int64)v13);
      }
      v7 = SystemCapabilitySecurityDescriptor;
      if ( SystemCapabilitySecurityDescriptor >= 0 )
        v7 = RtlCopySecurityDescriptor(pSourceSecurityDescriptor, a3);
    }
  }
LABEL_19:
  if ( pSourceSecurityDescriptor )
    LocalFree(pSourceSecurityDescriptor);
  FreeTransientObjectSecurityDescriptor(0);
  FreeTransientObjectSecurityDescriptor(v4);
  FreeTransientObjectSecurityDescriptor(v3);
  return v7;
}

```

## disassembly

```asm
0x180012100  mov     [rsp-28h+arg_0], rbx
0x180012105  push    rbp
0x180012106  push    rsi
0x180012107  push    rdi
0x180012108  push    r14
0x18001210a  push    r15
0x18001210c  mov     rbp, rsp
0x18001210f  sub     rsp, 40h
0x180012113  xor     esi, esi
0x180012115  xor     edi, edi
0x180012117  mov     [rbp+var_10], rsi
0x18001211b  mov     r15, r8
0x18001211e  mov     [rbp+SubStr], rdi
0x180012122  mov     [rbp+pSourceSecurityDescriptor], rsi
0x180012126  test    rdx, rdx
0x180012129  jz      loc_18001223F
0x18001212f  test    r8, r8
0x180012132  jz      loc_18001223F
0x180012138  lea     r8, [rbp+var_10]
0x18001213c  call    GetNormalizedObjectPath
0x180012141  mov     rsi, [rbp+var_10]
0x180012145  mov     ebx, eax
0x180012147  test    eax, eax
0x180012149  js      loc_180012244
0x18001214f  lea     rdx, [rbp+SubStr]
0x180012153  mov     rcx, rsi
0x180012156  call    QuerySecurityDescriptorValue
0x18001215b  mov     rdi, [rbp+SubStr]
0x18001215f  mov     ebx, eax
0x180012161  test    eax, eax
0x180012163  js      loc_180012244
0x180012169  cmp     dword ptr [rdi+4], 3
0x18001216d  jnz     short loc_1800121A1
0x18001216f  mov     ecx, [rdi+8]
0x180012172  call    AccessHlprAlloc
0x180012177  mov     r14, rax
0x18001217a  test    rax, rax
0x18001217d  jnz     short loc_180012189
0x18001217f  mov     ebx, 0C0000017h
0x180012184  jmp     loc_180012244
0x180012189  mov     r8d, [rdi+8]; Size
0x18001218d  lea     rdx, [rdi+0Ch]; Src
0x180012191  mov     rcx, r14; void *
0x180012194  call    memcpy_0
0x180012199  mov     [r15], r14
0x18001219c  jmp     loc_180012244
0x1800121a1  cmp     dword ptr [rdi+4], 1
0x1800121a5  jnz     short loc_1800121AD
0x1800121a7  cmp     dword ptr [rdi+8], 0
0x1800121ab  jnz     short loc_1800121B7
0x1800121ad  mov     ebx, 0C000090Bh
0x1800121b2  jmp     loc_180012244
0x1800121b7  mov     ebx, [rdi+8]
0x1800121ba  lea     r14, [rdi+0Ch]
0x1800121be  shr     rbx, 1
0x1800121c1  mov     eax, 7Bh ; '{'
0x1800121c6  mov     dword ptr [rbp+SubStr], 7Dh ; '}'
0x1800121cd  mov     rcx, r14; __int64
0x1800121d0  cmp     ax, [r14]
0x1800121d4  jnz     short loc_18001221C
0x1800121d6  lea     rdx, [rbp+SubStr]; SubStr
0x1800121da  call    cs:__imp_wcsstr
0x1800121e0  mov     r8, rax
0x1800121e3  test    rax, rax
0x1800121e6  jz      short loc_1800121AD
0x1800121e8  xor     eax, eax
0x1800121ea  lea     rcx, [r14+2]
0x1800121ee  mov     rdx, r8
0x1800121f1  mov     [r8], ax
0x1800121f5  sub     rdx, r14
0x1800121f8  lea     rax, [rbp+pSourceSecurityDescriptor]
0x1800121fc  sar     rdx, 1
0x1800121ff  add     r8, 2
0x180012203  dec     rdx
0x180012206  mov     [rsp+40h+var_20], rax
0x18001220b  sub     rbx, rdx
0x18001220e  inc     rdx
0x180012211  lea     r9, [rbx-2]
0x180012215  call    CreateSystemCapabilitySecurityDescriptor
0x18001221a  jmp     short loc_180012228
0x18001221c  lea     r8, [rbp+pSourceSecurityDescriptor]
0x180012220  mov     rdx, rbx
0x180012223  call    CreatePerUserSecurityDescriptor
0x180012228  mov     ebx, eax
0x18001222a  test    eax, eax
0x18001222c  js      short loc_180012244
0x18001222e  mov     rcx, [rbp+pSourceSecurityDescriptor]; pSourceSecurityDescriptor
0x180012232  mov     rdx, r15; pDestinationSecurityDescriptor
0x180012235  call    cs:__imp_RtlCopySecurityDescriptor
0x18001223b  mov     ebx, eax
0x18001223d  jmp     short loc_180012244
0x18001223f  mov     ebx, 0C000000Dh
0x180012244  mov     rcx, [rbp+pSourceSecurityDescriptor]; hMem
0x180012248  test    rcx, rcx
0x18001224b  jz      short loc_180012253
0x18001224d  call    cs:__imp_LocalFree
0x180012253  xor     ecx, ecx
0x180012255  call    FreeTransientObjectSecurityDescriptor
0x18001225a  mov     rcx, rdi
0x18001225d  call    FreeTransientObjectSecurityDescriptor
0x180012262  mov     rcx, rsi
0x180012265  call    FreeTransientObjectSecurityDescriptor
0x18001226a  mov     eax, ebx
0x18001226c  mov     rbx, [rsp+40h+arg_0]
0x180012271  add     rsp, 40h
0x180012275  pop     r15
0x180012277  pop     r14
0x180012279  pop     rdi
0x18001227a  pop     rsi
0x18001227b  pop     rbp
0x18001227c  retn
```
