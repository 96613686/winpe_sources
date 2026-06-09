# WSearchRegGetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong *,void *,ulong *)

- ea: `0x18000ccac`
- end: `0x18000cd48`
- name: `?WSearchRegGetValue@@YAJPEAUHKEY__@@PEB_W1KPEAKPEAX2@Z`
- size: `156`
- prototype: `int(HKEY, const wchar_t *, const wchar_t *, unsigned int, unsigned int *, void *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003cb0`
- `0x180003f10`
- `0x18000d000`
- `0x18000d554`

## callees

- `0x180001770`
- `0x18000c9d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd24`

## pseudocode

```c
LSTATUS __fastcall WSearchRegGetValue(
        const wchar_t *a1,
        wchar_t *a2,
        const wchar_t *a3,
        DWORD a4,
        unsigned int *a5,
        PVOID pvData,
        unsigned int *pcbData)
{
  bool v10; // al
  wchar_t *v11; // rdx
  wchar_t v13[264]; // [rsp+40h] [rbp-248h] BYREF

  v10 = MapRegistryKeyPath(a1, HKEY_LOCAL_MACHINE, a2, v13);
  v11 = v13;
  if ( !v10 )
    v11 = a2;
  return RegGetValueW(HKEY_LOCAL_MACHINE, v11, a3, a4, 0, pvData, pcbData);
}

```

## disassembly

```asm
0x18000ccac  push    rbx
0x18000ccae  push    rbp
0x18000ccaf  push    rsi
0x18000ccb0  push    rdi
0x18000ccb1  push    r14
0x18000ccb3  sub     rsp, 260h
0x18000ccba  mov     rax, cs:__security_cookie
0x18000ccc1  xor     rax, rsp
0x18000ccc4  mov     [rsp+288h+var_38], rax
0x18000cccc  mov     rdi, [rsp+288h+arg_28]
0x18000ccd4  mov     rbp, r8
0x18000ccd7  mov     rbx, [rsp+288h+arg_30]
0x18000ccdf  mov     r8, rdx; wchar_t *
0x18000cce2  mov     r14d, r9d
0x18000cce5  mov     rsi, rdx
0x18000cce8  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000ccef  lea     r9, [rsp+288h+var_248]; wchar_t *
0x18000ccf4  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18000ccf9  test    al, al
0x18000ccfb  mov     [rsp+288h+pcbData], rbx; pcbData
0x18000cd00  lea     rdx, [rsp+288h+var_248]
0x18000cd05  mov     [rsp+288h+pvData], rdi; pvData
0x18000cd0a  cmovz   rdx, rsi; lpSubKey
0x18000cd0e  mov     [rsp+288h+pdwType], 0; pdwType
0x18000cd17  mov     r9d, r14d; dwFlags
0x18000cd1a  mov     r8, rbp; lpValue
0x18000cd1d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000cd24  call    cs:__imp_RegGetValueW
0x18000cd2a  mov     rcx, [rsp+288h+var_38]
0x18000cd32  xor     rcx, rsp; StackCookie
0x18000cd35  call    __security_check_cookie
0x18000cd3a  add     rsp, 260h
0x18000cd41  pop     r14
0x18000cd43  pop     rdi
0x18000cd44  pop     rsi
0x18000cd45  pop     rbp
0x18000cd46  pop     rbx
0x18000cd47  retn
```
