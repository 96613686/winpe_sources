# CPxeProviderHandler::DumpState(void)

- ea: `0x180004c58`
- end: `0x180004dba`
- name: `?DumpState@CPxeProviderHandler@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(CPxeProviderHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003050`

## callees

- `0x180002a30`
- `0x180004c58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004c7d`
- `KERNEL32!EnterCriticalSection` at `0x180004ce3`
- `KERNEL32!EnterCriticalSection` at `0x180004c7d`
- `KERNEL32!EnterCriticalSection` at `0x180004ce3`
- `KERNEL32!LeaveCriticalSection` at `0x180004cb7`
- `KERNEL32!LeaveCriticalSection` at `0x180004cf9`
- `KERNEL32!LeaveCriticalSection` at `0x180004cb7`
- `KERNEL32!LeaveCriticalSection` at `0x180004cf9`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180004ccd`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180004ccd`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180004dae`

## pseudocode

```c
void __fastcall CPxeProviderHandler::DumpState(CPxeProviderHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  const wchar_t *v3; // r8
  CMRSWLock *v4; // r15
  __int64 v5; // rbx
  unsigned int *v6; // r14
  unsigned int *v7; // r8
  __int64 v8; // [rsp+20h] [rbp-68h]
  __int64 v9; // [rsp+28h] [rbp-60h]
  __int64 v10; // [rsp+30h] [rbp-58h]
  __int64 v11; // [rsp+38h] [rbp-50h]
  __int64 v12; // [rsp+40h] [rbp-48h]
  __int64 v13; // [rsp+48h] [rbp-40h]
  __int64 v14; // [rsp+50h] [rbp-38h]
  __int64 v15; // [rsp+58h] [rbp-30h]
  __int64 v16; // [rsp+60h] [rbp-28h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  v3 = L"Yes";
  if ( !*((_DWORD *)this + 81) )
    v3 = L"No";
  Trace(0x20000u, L"Pxe Providers Handler\n---------------------\nError State: %s\n", v3);
  LeaveCriticalSection(v1);
  v4 = (CPxeProviderHandler *)((char *)this + 200);
  CMRSWLock::ReaderLock((CPxeProviderHandler *)((char *)this + 200));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v5 = *((_QWORD *)this + 17);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( v5 )
  {
    v6 = (unsigned int *)*((_QWORD *)this + 17);
    while ( v6 )
    {
      v7 = v6;
      v6 = (unsigned int *)*((_QWORD *)v6 + 17);
      LODWORD(v16) = *((unsigned __int8 *)v7 + 15);
      LODWORD(v15) = *((unsigned __int8 *)v7 + 14);
      LODWORD(v14) = *((unsigned __int8 *)v7 + 13);
      LODWORD(v13) = *((unsigned __int8 *)v7 + 12);
      LODWORD(v12) = *((unsigned __int8 *)v7 + 11);
      LODWORD(v11) = *((unsigned __int8 *)v7 + 10);
      LODWORD(v10) = *((unsigned __int8 *)v7 + 9);
      LODWORD(v9) = *((unsigned __int8 *)v7 + 8);
      LODWORD(v8) = *((unsigned __int16 *)v7 + 3);
      Trace(
        0x20000u,
        L"Banned ID: {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}\n",
        *v7,
        *((unsigned __int16 *)v7 + 2),
        v8,
        v9,
        v10,
        v11,
        v12,
        v13,
        v14,
        v15,
        v16);
    }
  }
  CMRSWLock::ReaderRelease(v4);
}

```

## disassembly

```asm
0x180004c58  mov     [rsp+arg_0], rbx
0x180004c5d  mov     [rsp+arg_8], rbp
0x180004c62  mov     [rsp+arg_10], rsi
0x180004c67  push    rdi
0x180004c68  push    r14
0x180004c6a  push    r15
0x180004c6c  sub     rsp, 70h
0x180004c70  lea     rbx, [rcx+150h]
0x180004c77  mov     r14, rcx
0x180004c7a  mov     rcx, rbx; lpCriticalSection
0x180004c7d  call    cs:__imp_EnterCriticalSection
0x180004c84  nop     dword ptr [rax+rax+00h]
0x180004c89  cmp     dword ptr [r14+144h], 0
0x180004c91  lea     rax, aNo; "No"
0x180004c98  lea     r8, aYes; "Yes"
0x180004c9f  mov     ecx, 20000h; unsigned int
0x180004ca4  cmovz   r8, rax
0x180004ca8  lea     rdx, aPxeProvidersHa; "Pxe Providers Handler\n----------------"...
0x180004caf  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004cb4  mov     rcx, rbx; lpCriticalSection
0x180004cb7  call    cs:__imp_LeaveCriticalSection
0x180004cbe  nop     dword ptr [rax+rax+00h]
0x180004cc3  lea     r15, [r14+0C8h]
0x180004cca  mov     rcx, r15
0x180004ccd  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180004cd4  nop     dword ptr [rax+rax+00h]
0x180004cd9  lea     rdi, [r14+98h]
0x180004ce0  mov     rcx, rdi; lpCriticalSection
0x180004ce3  call    cs:__imp_EnterCriticalSection
0x180004cea  nop     dword ptr [rax+rax+00h]
0x180004cef  mov     rbx, [r14+88h]
0x180004cf6  mov     rcx, rdi; lpCriticalSection
0x180004cf9  call    cs:__imp_LeaveCriticalSection
0x180004d00  nop     dword ptr [rax+rax+00h]
0x180004d05  test    rbx, rbx
0x180004d08  jz      loc_180004D92
0x180004d0e  mov     r14, [r14+88h]
0x180004d15  jmp     short loc_180004D8D
0x180004d17  lea     r8, [r14]
0x180004d1a  mov     r14, [r14+88h]
0x180004d21  movzx   ecx, byte ptr [r8+0Eh]
0x180004d26  movzx   edx, byte ptr [r8+0Dh]
0x180004d2b  movzx   eax, byte ptr [r8+0Fh]
0x180004d30  movzx   r10d, byte ptr [r8+0Ch]
0x180004d35  movzx   r11d, byte ptr [r8+0Bh]
0x180004d3a  movzx   ebx, byte ptr [r8+0Ah]
0x180004d3f  movzx   edi, byte ptr [r8+9]
0x180004d44  movzx   esi, byte ptr [r8+8]
0x180004d49  movzx   ebp, word ptr [r8+6]
0x180004d4e  movzx   r9d, word ptr [r8+4]
0x180004d53  mov     r8d, [r8]
0x180004d56  mov     [rsp+88h+var_28], eax
0x180004d5a  mov     dword ptr [rsp+88h+var_30], ecx
0x180004d5e  mov     ecx, 20000h; unsigned int
0x180004d63  mov     dword ptr [rsp+88h+var_38], edx
0x180004d67  lea     rdx, aBannedId08x04x; "Banned ID: {%08X-%04X-%04X-%02X%02X-%02"...
0x180004d6e  mov     dword ptr [rsp+88h+var_40], r10d
0x180004d73  mov     dword ptr [rsp+88h+var_48], r11d
0x180004d78  mov     dword ptr [rsp+88h+var_50], ebx
0x180004d7c  mov     dword ptr [rsp+88h+var_58], edi
0x180004d80  mov     dword ptr [rsp+88h+var_60], esi
0x180004d84  mov     dword ptr [rsp+88h+var_68], ebp
0x180004d88  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004d8d  test    r14, r14
0x180004d90  jnz     short loc_180004D17
0x180004d92  mov     rcx, r15
0x180004d95  lea     r11, [rsp+88h+var_18]
0x180004d9a  mov     rbx, [r11+20h]
0x180004d9e  mov     rbp, [r11+28h]
0x180004da2  mov     rsi, [r11+30h]
0x180004da6  mov     rsp, r11
0x180004da9  pop     r15
0x180004dab  pop     r14
0x180004dad  pop     rdi
0x180004dae  jmp     cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
```
