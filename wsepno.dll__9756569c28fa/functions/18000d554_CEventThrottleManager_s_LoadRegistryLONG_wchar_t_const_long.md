# CEventThrottleManager::s_LoadRegistryLONG(wchar_t const *,long *)

- ea: `0x18000d554`
- end: `0x18000d589`
- name: `?s_LoadRegistryLONG@CEventThrottleManager@@CAJPEB_WPEAJ@Z`
- size: `53`
- prototype: `__int64 __fastcall(const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cee0`

## callees

- `0x18000ccac`

## pseudocode

```c
int __fastcall CEventThrottleManager::s_LoadRegistryLONG(wchar_t *a1, void *a2)
{
  unsigned int *v3; // [rsp+20h] [rbp-28h]
  unsigned int v4; // [rsp+60h] [rbp+18h] BYREF

  v4 = 4;
  return WSearchRegGetValue((HKEY)a1, L"Software\\Microsoft\\Windows Search\\Tracing", a1, 0x10u, v3, a2, &v4);
}

```

## disassembly

```asm
0x18000d554  sub     rsp, 48h
0x18000d558  lea     rax, [rsp+48h+arg_10]
0x18000d55d  mov     [rsp+48h+arg_10], 4
0x18000d565  mov     [rsp+48h+var_18], rax; unsigned int *
0x18000d56a  mov     r9d, 10h; unsigned int
0x18000d570  mov     [rsp+48h+var_20], rdx; void *
0x18000d575  mov     r8, rcx; wchar_t *
0x18000d578  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows Search\\Tr"...
0x18000d57f  call    ?WSearchRegGetValue@@YAJPEAUHKEY__@@PEB_W1KPEAKPEAX2@Z; WSearchRegGetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong *,void *,ulong *)
0x18000d584  add     rsp, 48h
0x18000d588  retn
```
