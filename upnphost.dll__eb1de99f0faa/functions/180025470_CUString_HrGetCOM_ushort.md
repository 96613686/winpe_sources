# CUString::HrGetCOM(ushort * *)

- ea: `0x180025470`
- end: `0x18002554b`
- name: `?HrGetCOM@CUString@@QEBAJPEAPEAG@Z`
- size: `219`
- prototype: `__int64 __fastcall(CUString *__hidden this, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011e80`
- `0x180014770`
- `0x180014c58`
- `0x180019b70`
- `0x180024bf0`
- `0x1800487f0`
- `0x1800489d0`

## callees

- `0x180025470`
- `0x180038324`
- `0x180038ce4`
- `0x180043124`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800254a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800254a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002553e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002553e`

## pseudocode

```c
__int64 __fastcall CUString::HrGetCOM(CUString *this, LPVOID *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  size_t v5; // rsi
  unsigned __int16 *v6; // rax
  size_t v7; // r8
  size_t v8; // rdx
  wchar_t *v9; // rcx
  HRESULT v10; // ebx
  size_t *v11; // r8
  const wchar_t *v12; // r9
  bool v13; // zf
  size_t v15; // [rsp+20h] [rbp-38h]

  if ( a2 )
  {
    v3 = *(_QWORD *)this;
    if ( v3 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)(v3 + 2 * v4) );
    }
    else
    {
      v4 = 0;
    }
    v5 = v4 + 1;
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v4 + 1));
    *a2 = v6;
    if ( !v6 )
    {
      v10 = -2147024882;
      goto LABEL_13;
    }
    v10 = StringValidateDestW(v6, v5, v7);
    if ( v10 < 0 )
    {
      if ( v5 )
      {
        *v9 = 0;
LABEL_19:
        CoTaskMemFree(*a2);
        v13 = v10 == 0;
        *a2 = 0;
LABEL_9:
        if ( v13 )
          return (unsigned int)v10;
LABEL_13:
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_a0ae7d175179382b7ee5ae7e1ec9cc2a_Traceguids,
            (unsigned int)v10);
        return (unsigned int)v10;
      }
    }
    else
    {
      v10 = StringCopyWorkerW(v9, v8, v11, v12, v15);
    }
    v13 = v10 == 0;
    if ( v10 >= 0 )
      goto LABEL_9;
    goto LABEL_19;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180025470  push    rbx
0x180025472  push    rbp
0x180025473  push    rsi
0x180025474  push    rdi
0x180025475  sub     rsp, 38h
0x180025479  xor     ebp, ebp
0x18002547b  mov     rdi, rdx
0x18002547e  mov     rbx, rcx
0x180025481  test    rdx, rdx
0x180025484  jz      short loc_1800254EC
0x180025486  mov     rcx, [rcx]
0x180025489  test    rcx, rcx
0x18002548c  jz      loc_18002552B
0x180025492  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025496  inc     rax
0x180025499  cmp     [rcx+rax*2], bp
0x18002549d  jnz     short loc_180025496
0x18002549f  lea     rsi, [rax+1]
0x1800254a3  lea     rcx, [rsi+rsi]; cb
0x1800254a7  call    cs:__imp_CoTaskMemAlloc
0x1800254ad  mov     [rdi], rax
0x1800254b0  mov     rcx, rax; pszDest
0x1800254b3  test    rax, rax
0x1800254b6  jz      short loc_1800254F3
0x1800254b8  cmp     [rbx], rbp
0x1800254bb  lea     r9, dword_180060F84
0x1800254c2  mov     rdx, rsi; cchDest
0x1800254c5  cmovnz  r9, [rbx]
0x1800254c9  call    StringValidateDestW
0x1800254ce  mov     ebx, eax
0x1800254d0  test    eax, eax
0x1800254d2  js      short loc_180025533
0x1800254d4  call    StringCopyWorkerW
0x1800254d9  mov     ebx, eax
0x1800254db  test    ebx, ebx
0x1800254dd  js      short loc_18002553B
0x1800254df  jnz     short loc_1800254F8
0x1800254e1  mov     eax, ebx
0x1800254e3  add     rsp, 38h
0x1800254e7  pop     rdi
0x1800254e8  pop     rsi
0x1800254e9  pop     rbp
0x1800254ea  pop     rbx
0x1800254eb  retn
0x1800254ec  mov     eax, 80004003h
0x1800254f1  jmp     short loc_1800254E3
0x1800254f3  mov     ebx, 8007000Eh
0x1800254f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254ff  lea     rax, WPP_GLOBAL_Control
0x180025506  cmp     rcx, rax
0x180025509  jz      short loc_1800254E1
0x18002550b  test    byte ptr [rcx+1Ch], 1
0x18002550f  jz      short loc_1800254E1
0x180025511  mov     rcx, [rcx+10h]
0x180025515  lea     r8, WPP_a0ae7d175179382b7ee5ae7e1ec9cc2a_Traceguids
0x18002551c  mov     edx, 0Bh
0x180025521  mov     r9d, ebx
0x180025524  call    WPP_SF_d
0x180025529  jmp     short loc_1800254E1
0x18002552b  mov     rax, rbp
0x18002552e  jmp     loc_18002549F
0x180025533  test    rsi, rsi
0x180025536  jz      short loc_1800254DB
0x180025538  mov     [rcx], bp
0x18002553b  mov     rcx, [rdi]; pv
0x18002553e  call    cs:__imp_CoTaskMemFree
0x180025544  test    ebx, ebx
0x180025546  mov     [rdi], rbp
0x180025549  jmp     short loc_1800254DF
```
