# SafeRegQueryValueCchAllocHelper(ulong,HKEY__ *,wchar_t const *,wchar_t * *,int *,int *)

- ea: `0x18003212c`
- end: `0x180032249`
- name: `?SafeRegQueryValueCchAllocHelper@@YAJKPEAUHKEY__@@PEB_WPEAPEA_WPEAH3@Z`
- size: `285`
- prototype: `int(unsigned int, HKEY, const wchar_t *, wchar_t **, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18000ff74`

## callees

- `0x180005f64`
- `0x18000a60c`
- `0x180031fb4`
- `0x18003212c`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032195`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032195`

## string_xrefs

- `0x180032181`: `RootDirectory`
- `0x1800321e6`: `RootDirectory`

## pseudocode

```c
__int64 __fastcall SafeRegQueryValueCchAllocHelper(
        __int64 a1,
        HKEY a2,
        const wchar_t *a3,
        wchar_t **a4,
        int *a5,
        int *a6)
{
  void *v6; // rdi
  int v7; // ebp
  signed int v10; // ebx
  LSTATUS v11; // eax
  signed int v12; // ebx
  void *v13; // rax
  __int64 v14; // rcx
  signed int v15; // eax
  int v17; // [rsp+40h] [rbp-48h] BYREF
  int v18; // [rsp+44h] [rbp-44h] BYREF
  DWORD v19; // [rsp+48h] [rbp-40h] BYREF

  v6 = 0;
  v7 = 0;
  v18 = 0;
  v17 = 0;
  v10 = -2147024809;
  if ( !a4 )
    goto LABEL_11;
  v19 = 0;
  v11 = RegQueryValueExW(a2, L"RootDirectory", 0, 0, 0, &v19);
  if ( !v11 || v11 == 234 )
  {
    v12 = (v19 >> 1) + 2;
    v13 = SusAlloc(2LL * v12);
    v6 = v13;
    if ( !v13 )
    {
      v10 = -2147024882;
      goto LABEL_11;
    }
    v15 = SafeRegQueryValueCchHelper(v14, a2, L"RootDirectory", v13, v12, &v18, &v17);
    v7 = v17;
    v10 = v15;
  }
  else
  {
    v10 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v10 = v11;
  }
  if ( v10 < 0 )
  {
LABEL_11:
    CSusBaseAllocTag<942762101>::operator delete(v6);
    v6 = 0;
    if ( !a4 )
      goto LABEL_13;
  }
  *a4 = (wchar_t *)v6;
LABEL_13:
  if ( a6 )
    *a6 = v7;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003212c  mov     r11, rsp
0x18003212f  mov     [r11+8], rbx
0x180032133  push    rbp
0x180032134  push    rsi
0x180032135  push    rdi
0x180032136  push    r14
0x180032138  push    r15
0x18003213a  sub     rsp, 60h
0x18003213e  mov     rax, cs:__security_cookie
0x180032145  xor     rax, rsp
0x180032148  mov     [rsp+88h+var_38], rax
0x18003214d  mov     rsi, [rsp+88h+arg_28]
0x180032155  xor     edi, edi
0x180032157  xor     ebp, ebp
0x180032159  mov     [rsp+88h+var_44], edi
0x18003215d  mov     [rsp+88h+var_48], ebp
0x180032161  mov     r14, r9
0x180032164  mov     r15, rdx
0x180032167  mov     ebx, 80070057h
0x18003216c  test    r9, r9
0x18003216f  jz      loc_18003220D
0x180032175  lea     rax, [r11-40h]
0x180032179  mov     [rsp+88h+var_40], edi
0x18003217d  mov     [r11-60h], rax
0x180032181  lea     rdx, ?c_szRootDirectoryRegValue@@3QB_WB; "RootDirectory"
0x180032188  xor     r9d, r9d; lpType
0x18003218b  mov     [r11-68h], rdi
0x18003218f  xor     r8d, r8d; lpReserved
0x180032192  mov     rcx, r15; hKey
0x180032195  call    cs:__imp_RegQueryValueExW
0x18003219b  test    eax, eax
0x18003219d  jz      short loc_1800321B6
0x18003219f  cmp     eax, 0EAh
0x1800321a4  jz      short loc_1800321B6
0x1800321a6  movzx   ebx, ax
0x1800321a9  or      ebx, 80070000h
0x1800321af  test    eax, eax
0x1800321b1  cmovle  ebx, eax
0x1800321b4  jmp     short loc_180032209
0x1800321b6  mov     ebx, [rsp+88h+var_40]
0x1800321ba  shr     ebx, 1
0x1800321bc  add     ebx, 2
0x1800321bf  movsxd  rcx, ebx
0x1800321c2  add     rcx, rcx; unsigned __int64
0x1800321c5  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x1800321ca  mov     rdi, rax
0x1800321cd  test    rax, rax
0x1800321d0  jnz     short loc_1800321D9
0x1800321d2  mov     ebx, 8007000Eh
0x1800321d7  jmp     short loc_18003220D
0x1800321d9  lea     rax, [rsp+88h+var_48]
0x1800321de  mov     r9, rdi
0x1800321e1  mov     [rsp+88h+var_58], rax
0x1800321e6  lea     r8, ?c_szRootDirectoryRegValue@@3QB_WB; "RootDirectory"
0x1800321ed  lea     rax, [rsp+88h+var_44]
0x1800321f2  mov     rdx, r15
0x1800321f5  mov     [rsp+88h+var_60], rax
0x1800321fa  mov     [rsp+88h+var_68], ebx
0x1800321fe  call    SafeRegQueryValueCchHelper
0x180032203  mov     ebp, [rsp+88h+var_48]
0x180032207  mov     ebx, eax
0x180032209  test    ebx, ebx
0x18003220b  jns     short loc_18003221C
0x18003220d  mov     rcx, rdi; lpMem
0x180032210  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180032215  xor     edi, edi
0x180032217  test    r14, r14
0x18003221a  jz      short loc_18003221F
0x18003221c  mov     [r14], rdi
0x18003221f  test    rsi, rsi
0x180032222  jz      short loc_180032226
0x180032224  mov     [rsi], ebp
0x180032226  mov     eax, ebx
0x180032228  mov     rcx, [rsp+88h+var_38]
0x18003222d  xor     rcx, rsp; StackCookie
0x180032230  call    __security_check_cookie
0x180032235  mov     rbx, [rsp+88h+arg_0]
0x18003223d  add     rsp, 60h
0x180032241  pop     r15
0x180032243  pop     r14
0x180032245  pop     rdi
0x180032246  pop     rsi
0x180032247  pop     rbp
0x180032248  retn
```
