# CInterfaceMonitor::Shutdown(void)

- ea: `0x1800105f0`
- end: `0x180010637`
- name: `?Shutdown@CInterfaceMonitor@@QEAAKXZ`
- size: `71`
- prototype: `unsigned int __fastcall(CInterfaceMonitor *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d380`
- `0x18000fd54`
- `0x180013638`
- `0x18001393c`

## callees

- `0x180010534`
- `0x1800105f0`

## import_xrefs

- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001061a`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001061a`

## pseudocode

```c
__int64 __fastcall CInterfaceMonitor::Shutdown(CInterfaceMonitor *this)
{
  void *v2; // rcx

  CNetworkChangeMonitor<CInterfaceMonitor>::Shutdown((LPCRITICAL_SECTION)this + 1);
  CNetworkChangeMonitor<CInterfaceMonitor>::Shutdown((LPCRITICAL_SECTION)((char *)this + 352));
  v2 = (void *)*((_QWORD *)this + 84);
  if ( v2 )
  {
    WdsPrivateHpFree(v2);
    *((_QWORD *)this + 84) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800105f0  push    rbx
0x1800105f2  sub     rsp, 20h
0x1800105f6  mov     rbx, rcx
0x1800105f9  add     rcx, 28h ; '('; lpCriticalSection
0x1800105fd  call    ?Shutdown@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAAKXZ; CNetworkChangeMonitor<CInterfaceMonitor>::Shutdown(void)
0x180010602  lea     rcx, [rbx+160h]; lpCriticalSection
0x180010609  call    ?Shutdown@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAAKXZ; CNetworkChangeMonitor<CInterfaceMonitor>::Shutdown(void)
0x18001060e  mov     rcx, [rbx+2A0h]
0x180010615  test    rcx, rcx
0x180010618  jz      short loc_18001062E
0x18001061a  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180010621  nop     dword ptr [rax+rax+00h]
0x180010626  and     qword ptr [rbx+2A0h], 0
0x18001062e  xor     eax, eax
0x180010630  add     rsp, 20h
0x180010634  pop     rbx
0x180010635  retn
```
