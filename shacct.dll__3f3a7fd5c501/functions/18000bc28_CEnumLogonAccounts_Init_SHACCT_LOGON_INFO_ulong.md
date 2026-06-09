# CEnumLogonAccounts::Init(_SHACCT_LOGON_INFO *,ulong)

- ea: `0x18000bc28`
- end: `0x18000bc88`
- name: `?Init@CEnumLogonAccounts@@QEAAJPEAU_SHACCT_LOGON_INFO@@K@Z`
- size: `96`
- prototype: `int(CEnumLogonAccounts *__hidden this, struct _SHACCT_LOGON_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800136b0`

## callees

- `0x18000bc28`
- `0x180016ce9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc5e`

## pseudocode

```c
__int64 __fastcall CEnumLogonAccounts::Init(CEnumLogonAccounts *this, struct _SHACCT_LOGON_INFO *a2, unsigned int a3)
{
  unsigned int v5; // ebx
  SIZE_T v6; // rbp
  void *v7; // rax

  v5 = -2147024809;
  if ( a2 )
  {
    v5 = 0;
    *((_DWORD *)this + 3) = a3;
    if ( a3 )
    {
      v5 = -2147024882;
      v6 = 528LL * a3;
      v7 = CoTaskMemAlloc(v6);
      *((_QWORD *)this + 2) = v7;
      if ( v7 )
      {
        memcpy_0(v7, a2, v6);
        return 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000bc28  push    rbx
0x18000bc2a  push    rbp
0x18000bc2b  push    rsi
0x18000bc2c  push    rdi
0x18000bc2d  sub     rsp, 28h
0x18000bc31  mov     rsi, rdx
0x18000bc34  mov     rdi, rcx
0x18000bc37  mov     ebx, 80070057h
0x18000bc3c  test    rdx, rdx
0x18000bc3f  jz      short loc_18000BC7D
0x18000bc41  xor     ebx, ebx
0x18000bc43  mov     [rcx+0Ch], r8d
0x18000bc47  test    r8d, r8d
0x18000bc4a  jz      short loc_18000BC7D
0x18000bc4c  mov     eax, r8d
0x18000bc4f  mov     ebx, 8007000Eh
0x18000bc54  imul    rbp, rax, 210h
0x18000bc5b  mov     rcx, rbp; cb
0x18000bc5e  call    cs:__imp_CoTaskMemAlloc
0x18000bc64  mov     [rdi+10h], rax
0x18000bc68  test    rax, rax
0x18000bc6b  jz      short loc_18000BC7D
0x18000bc6d  mov     r8, rbp; Size
0x18000bc70  mov     rdx, rsi; Src
0x18000bc73  mov     rcx, rax; void *
0x18000bc76  call    memcpy_0
0x18000bc7b  xor     ebx, ebx
0x18000bc7d  mov     eax, ebx
0x18000bc7f  add     rsp, 28h
0x18000bc83  pop     rdi
0x18000bc84  pop     rsi
0x18000bc85  pop     rbp
0x18000bc86  pop     rbx
0x18000bc87  retn
```
