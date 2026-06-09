# _GetStringArrayFromUSKey

- ea: `0x18003b6f0`
- end: `0x18003b8d9`
- name: `_GetStringArrayFromUSKey`
- size: `489`
- prototype: `__int64 __fastcall(HUSKEY hRelativeUSKey, LPCWSTR pwzPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18003afcc`

## callees

- `0x180001610`
- `0x18000161c`
- `0x18003b6f0`
- `0x18003b8e0`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!SHRegCloseUSKey` at `0x18003b8ae`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b8ae`
- `SHLWAPI!SHRegEnumUSValueW` at `0x18003b812`
- `SHLWAPI!SHRegEnumUSValueW` at `0x18003b812`
- `SHLWAPI!SHRegQueryInfoUSKeyW` at `0x18003b795`
- `SHLWAPI!SHRegQueryInfoUSKeyW` at `0x18003b795`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18003b765`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18003b765`

## pseudocode

```c
__int64 __fastcall GetStringArrayFromUSKey(HUSKEY hRelativeUSKey, LPCWSTR pwzPath, _QWORD *a3, DWORD *a4)
{
  int StringFromUSValue; // esi
  DWORD v9; // eax
  _WORD **v10; // rdi
  DWORD v11; // r14d
  DWORD v12; // ebx
  DWORD i; // r14d
  _WORD *v14; // rcx
  DWORD pcValues; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchValueName; // [rsp+44h] [rbp-BCh] BYREF
  HUSKEY phNewUSKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  phNewUSKey = 0;
  pcValues = 0;
  StringFromUSValue = 0;
  memset_0(pszValueName, 0, 0x208u);
  pcchValueName = 0;
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, hRelativeUSKey, &phNewUSKey, 0) )
  {
    *a3 = 0;
    *a4 = 0;
  }
  else if ( SHRegQueryInfoUSKeyW(phNewUSKey, 0, 0, &pcValues, 0, SHREGENUM_DEFAULT) || (v9 = pcValues, pcValues <= 1) )
  {
    StringFromUSValue = -2147024809;
  }
  else
  {
    --pcValues;
    v10 = (_WORD **)operator new(saturated_mul(v9 - 1, 8u));
    v11 = 0;
    v12 = 0;
    while ( 1 )
    {
      pcchValueName = 260;
      if ( v12 >= pcValues
        || SHRegEnumUSValueW(phNewUSKey, v11, pszValueName, &pcchValueName, 0, 0, 0, SHREGENUM_DEFAULT) )
      {
        break;
      }
      if ( pszValueName[0] )
      {
        StringFromUSValue = GetStringFromUSValue(phNewUSKey, pszValueName, 0);
        if ( StringFromUSValue < 0 )
          goto LABEL_16;
        if ( *v10[v12] )
          ++v12;
      }
      ++v11;
    }
    if ( v12 )
    {
      *a3 = v10;
      *a4 = v12;
      goto LABEL_23;
    }
    StringFromUSValue = -2147024809;
LABEL_16:
    if ( v10 )
    {
      for ( i = 0; i < v12; ++i )
      {
        v14 = v10[i];
        if ( v14 )
        {
          operator delete(v14);
          v10[i] = 0;
        }
      }
      operator delete(v10);
    }
  }
LABEL_23:
  if ( phNewUSKey )
    SHRegCloseUSKey(phNewUSKey);
  return (unsigned int)StringFromUSValue;
}

```

## disassembly

```asm
0x18003b6f0  push    rbp
0x18003b6f2  push    rbx
0x18003b6f3  push    rsi
0x18003b6f4  push    rdi
0x18003b6f5  push    r12
0x18003b6f7  push    r13
0x18003b6f9  push    r14
0x18003b6fb  push    r15
0x18003b6fd  lea     rbp, [rsp-178h]
0x18003b705  sub     rsp, 278h
0x18003b70c  mov     rax, cs:__security_cookie
0x18003b713  xor     rax, rsp
0x18003b716  mov     [rbp+1B0h+var_50], rax
0x18003b71d  xor     r15d, r15d
0x18003b720  mov     r12, r8
0x18003b723  mov     rdi, rdx
0x18003b726  mov     [rsp+2B0h+phNewUSKey], r15
0x18003b72b  mov     rbx, rcx
0x18003b72e  mov     [rsp+2B0h+pcValues], r15d
0x18003b733  xor     edx, edx; Val
0x18003b735  lea     rcx, [rsp+2B0h+pszValueName]; void *
0x18003b73a  mov     r8d, 208h; Size
0x18003b740  mov     esi, r15d
0x18003b743  mov     r13, r9
0x18003b746  call    memset_0
0x18003b74b  lea     r9, [rsp+2B0h+phNewUSKey]; phNewUSKey
0x18003b750  mov     [rsp+2B0h+pcchValueName], r15d
0x18003b755  mov     r8, rbx; hRelativeUSKey
0x18003b758  mov     [rsp+2B0h+fIgnoreHKCU], r15d; fIgnoreHKCU
0x18003b75d  mov     edx, 20019h; samDesired
0x18003b762  mov     rcx, rdi; pwzPath
0x18003b765  call    cs:__imp_SHRegOpenUSKeyW
0x18003b76b  test    eax, eax
0x18003b76d  jz      short loc_18003B77C
0x18003b76f  mov     [r12], r15
0x18003b773  mov     [r13+0], r15d
0x18003b777  jmp     loc_18003B8A4
0x18003b77c  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSKey
0x18003b781  lea     r9, [rsp+2B0h+pcValues]; pcValues
0x18003b786  mov     [rsp+2B0h+enumRegFlags], r15d; enumRegFlags
0x18003b78b  xor     r8d, r8d; pcchMaxSubKeyLen
0x18003b78e  xor     edx, edx; pcSubKeys
0x18003b790  mov     qword ptr [rsp+2B0h+fIgnoreHKCU], r15; pcchMaxValueNameLen
0x18003b795  call    cs:__imp_SHRegQueryInfoUSKeyW
0x18003b79b  test    eax, eax
0x18003b79d  jz      short loc_18003B7A9
0x18003b79f  mov     esi, 80070057h
0x18003b7a4  jmp     loc_18003B8A4
0x18003b7a9  mov     eax, [rsp+2B0h+pcValues]
0x18003b7ad  cmp     eax, 1
0x18003b7b0  jbe     short loc_18003B79F
0x18003b7b2  dec     eax
0x18003b7b4  mov     ecx, eax
0x18003b7b6  mov     [rsp+2B0h+pcValues], eax
0x18003b7ba  mov     eax, 8
0x18003b7bf  mul     rcx
0x18003b7c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b7c9  cmovb   rax, rcx
0x18003b7cd  mov     rcx, rax; Size
0x18003b7d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b7d5  mov     rdi, rax
0x18003b7d8  mov     r14d, r15d
0x18003b7db  mov     ebx, r15d
0x18003b7de  mov     [rsp+2B0h+pcchValueName], 104h
0x18003b7e6  cmp     ebx, [rsp+2B0h+pcValues]
0x18003b7ea  jnb     short loc_18003B858
0x18003b7ec  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSkey
0x18003b7f1  lea     r9, [rsp+2B0h+pcchValueName]; pcchValueName
0x18003b7f6  mov     [rsp+2B0h+var_278], r15d; enumRegFlags
0x18003b7fb  lea     r8, [rsp+2B0h+pszValueName]; pszValueName
0x18003b800  mov     [rsp+2B0h+pcbData], r15; pcbData
0x18003b805  mov     edx, r14d; dwIndex
0x18003b808  mov     qword ptr [rsp+2B0h+enumRegFlags], r15; pvData
0x18003b80d  mov     qword ptr [rsp+2B0h+fIgnoreHKCU], r15; pdwType
0x18003b812  call    cs:__imp_SHRegEnumUSValueW
0x18003b818  test    eax, eax
0x18003b81a  jnz     short loc_18003B858
0x18003b81c  cmp     [rsp+2B0h+pszValueName], r15w
0x18003b822  jz      short loc_18003B853
0x18003b824  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSKey
0x18003b829  lea     rdx, [rsp+2B0h+pszValueName]; pszValue
0x18003b82e  mov     eax, ebx
0x18003b830  xor     r8d, r8d; pvDefaultData
0x18003b833  lea     r15, [rdi+rax*8]
0x18003b837  mov     r9, r15
0x18003b83a  call    _GetStringFromUSValue
0x18003b83f  mov     esi, eax
0x18003b841  test    eax, eax
0x18003b843  js      short loc_18003B863
0x18003b845  mov     rcx, [r15]
0x18003b848  xor     r15d, r15d
0x18003b84b  cmp     [rcx], r15w
0x18003b84f  jz      short loc_18003B853
0x18003b851  inc     ebx
0x18003b853  inc     r14d
0x18003b856  jmp     short loc_18003B7DE
0x18003b858  test    ebx, ebx
0x18003b85a  jnz     short loc_18003B89C
0x18003b85c  mov     esi, 80070057h
0x18003b861  jmp     short loc_18003B866
0x18003b863  xor     r15d, r15d
0x18003b866  test    rdi, rdi
0x18003b869  jz      short loc_18003B8A4
0x18003b86b  mov     r14d, r15d
0x18003b86e  test    ebx, ebx
0x18003b870  jz      short loc_18003B892
0x18003b872  xor     r12d, r12d
0x18003b875  mov     r15d, r14d
0x18003b878  mov     rcx, [rdi+r15*8]; Block
0x18003b87c  test    rcx, rcx
0x18003b87f  jz      short loc_18003B88A
0x18003b881  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003b886  mov     [rdi+r15*8], r12
0x18003b88a  inc     r14d
0x18003b88d  cmp     r14d, ebx
0x18003b890  jb      short loc_18003B875
0x18003b892  mov     rcx, rdi; Block
0x18003b895  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003b89a  jmp     short loc_18003B8A4
0x18003b89c  mov     [r12], rdi
0x18003b8a0  mov     [r13+0], ebx
0x18003b8a4  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSKey
0x18003b8a9  test    rcx, rcx
0x18003b8ac  jz      short loc_18003B8B4
0x18003b8ae  call    cs:__imp_SHRegCloseUSKey
0x18003b8b4  mov     eax, esi
0x18003b8b6  mov     rcx, [rbp+1B0h+var_50]
0x18003b8bd  xor     rcx, rsp; StackCookie
0x18003b8c0  call    __security_check_cookie
0x18003b8c5  add     rsp, 278h
0x18003b8cc  pop     r15
0x18003b8ce  pop     r14
0x18003b8d0  pop     r13
0x18003b8d2  pop     r12
0x18003b8d4  pop     rdi
0x18003b8d5  pop     rsi
0x18003b8d6  pop     rbx
0x18003b8d7  pop     rbp
0x18003b8d8  retn
```
