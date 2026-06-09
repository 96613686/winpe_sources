# CACConnectionPage::ConvertProfileSsidToDisplaySsid(_DOT11_SSID *,ushort * *)

- ea: `0x18000db78`
- end: `0x18000dc31`
- name: `?ConvertProfileSsidToDisplaySsid@CACConnectionPage@@AEAAKPEAU_DOT11_SSID@@PEAPEAG@Z`
- size: `185`
- prototype: `__int64 __fastcall(CACConnectionPage *this, struct _DOT11_SSID *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000ef50`
- `0x18000fe78`

## callees

- `0x18000db78`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000dbe0`
- `KERNEL32!GetLastError` at `0x18000dbe0`
- `KERNEL32!HeapAlloc` at `0x18000dbd2`
- `KERNEL32!HeapAlloc` at `0x18000dbd2`
- `KERNEL32!GetProcessHeap` at `0x18000dbc1`
- `KERNEL32!GetProcessHeap` at `0x18000dc12`
- `KERNEL32!GetProcessHeap` at `0x18000dbc1`
- `KERNEL32!GetProcessHeap` at `0x18000dc12`
- `KERNEL32!HeapFree` at `0x18000dc20`
- `KERNEL32!HeapFree` at `0x18000dc20`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18000dba9`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18000dbfc`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18000dba9`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18000dbfc`

## pseudocode

```c
__int64 __fastcall CACConnectionPage::ConvertProfileSsidToDisplaySsid(
        CACConnectionPage *this,
        struct _DOT11_SSID *a2,
        unsigned __int16 **a3)
{
  DWORD v5; // eax
  DWORD LastError; // ebx
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rdi
  HANDLE v10; // rax
  unsigned int v12; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]

  v13 = HIDWORD(this);
  *a3 = 0;
  v12 = 0;
  v5 = WlanUtf8SsidToDisplayName(a2, 1, 0, &v12);
  LastError = v5;
  if ( v5 == 122 || !v5 )
  {
    v7 = 2LL * v12;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 8u, v7);
    if ( v9 || (LastError = GetLastError()) == 0 )
    {
      LastError = WlanUtf8SsidToDisplayName(a2, 1, v9, &v12);
      if ( LastError )
      {
        if ( v9 )
        {
          v10 = GetProcessHeap();
          HeapFree(v10, 0, v9);
        }
      }
      else
      {
        *a3 = (unsigned __int16 *)v9;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000db78  mov     [rsp+arg_0], rcx
0x18000db7d  push    rbx
0x18000db7e  push    rbp
0x18000db7f  push    rsi
0x18000db80  push    rdi
0x18000db81  sub     rsp, 28h
0x18000db85  mov     rbp, rdx
0x18000db88  mov     qword ptr [r8], 0
0x18000db8f  mov     rsi, r8
0x18000db92  mov     dword ptr [rsp+48h+arg_0], 0
0x18000db9a  xor     r8d, r8d
0x18000db9d  lea     r9, [rsp+48h+arg_0]
0x18000dba2  mov     rcx, rbp
0x18000dba5  lea     edx, [r8+1]
0x18000dba9  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18000dbaf  mov     ebx, eax
0x18000dbb1  cmp     eax, 7Ah ; 'z'
0x18000dbb4  jz      short loc_18000DBBA
0x18000dbb6  test    eax, eax
0x18000dbb8  jnz     short loc_18000DC26
0x18000dbba  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18000dbbe  add     rbx, rbx
0x18000dbc1  call    cs:__imp_GetProcessHeap
0x18000dbc7  mov     r8, rbx; dwBytes
0x18000dbca  mov     edx, 8; dwFlags
0x18000dbcf  mov     rcx, rax; hHeap
0x18000dbd2  call    cs:__imp_HeapAlloc
0x18000dbd8  mov     rdi, rax
0x18000dbdb  test    rax, rax
0x18000dbde  jnz     short loc_18000DBEC
0x18000dbe0  call    cs:__imp_GetLastError
0x18000dbe6  mov     ebx, eax
0x18000dbe8  test    eax, eax
0x18000dbea  jnz     short loc_18000DC26
0x18000dbec  lea     r9, [rsp+48h+arg_0]
0x18000dbf1  mov     r8, rdi
0x18000dbf4  mov     edx, 1
0x18000dbf9  mov     rcx, rbp
0x18000dbfc  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18000dc02  mov     ebx, eax
0x18000dc04  test    eax, eax
0x18000dc06  jnz     short loc_18000DC0D
0x18000dc08  mov     [rsi], rdi
0x18000dc0b  jmp     short loc_18000DC26
0x18000dc0d  test    rdi, rdi
0x18000dc10  jz      short loc_18000DC26
0x18000dc12  call    cs:__imp_GetProcessHeap
0x18000dc18  mov     r8, rdi; lpMem
0x18000dc1b  xor     edx, edx; dwFlags
0x18000dc1d  mov     rcx, rax; hHeap
0x18000dc20  call    cs:__imp_HeapFree
0x18000dc26  mov     eax, ebx
0x18000dc28  add     rsp, 28h
0x18000dc2c  pop     rdi
0x18000dc2d  pop     rsi
0x18000dc2e  pop     rbp
0x18000dc2f  pop     rbx
0x18000dc30  retn
```
