# WimPublishConfigChangeNotification

- ea: `0x14002b73c`
- end: `0x14002b775`
- name: `WimPublishConfigChangeNotification`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14002ad28`
- `0x14002ba8c`

## callees

- `0x140011640`
- `0x14002b73c`

## pseudocode

```c
__int64 (__fastcall *WimPublishConfigChangeNotification())(_QWORD, _QWORD, _QWORD)
{
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD); // rax

  result = ZwUpdateWnfStateDataWrapper;
  if ( ZwUpdateWnfStateDataWrapper )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ZwUpdateWnfStateDataWrapper(
                                                             &WNF_WOF_OVERLAY_CONFIGURATION_CHANGE,
                                                             0,
                                                             0);
  return result;
}

```

## disassembly

```asm
0x14002b73c  sub     rsp, 48h
0x14002b740  mov     rax, cs:ZwUpdateWnfStateDataWrapper
0x14002b747  xor     ecx, ecx
0x14002b749  test    rax, rax
0x14002b74c  jz      short loc_14002B76F
0x14002b74e  mov     [rsp+48h+var_18], ecx
0x14002b752  xor     r9d, r9d
0x14002b755  mov     [rsp+48h+var_20], ecx
0x14002b759  xor     r8d, r8d
0x14002b75c  mov     [rsp+48h+var_28], rcx
0x14002b761  xor     edx, edx
0x14002b763  lea     rcx, WNF_WOF_OVERLAY_CONFIGURATION_CHANGE
0x14002b76a  call    _guard_dispatch_icall
0x14002b76f  add     rsp, 48h
0x14002b773  retn
```
