# CTrkWksSvc::RaiseIfStopped(void)

- ea: `0x180004f34`
- end: `0x180004f5a`
- name: `?RaiseIfStopped@CTrkWksSvc@@QEBAXXZ`
- size: `38`
- prototype: `void __fastcall(CTrkWksSvc *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022d4`
- `0x180003798`
- `0x1800053b0`
- `0x18000756c`

## callees

- `0x180004f34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004f53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004f53`

## pseudocode

```c
void __fastcall CTrkWksSvc::RaiseIfStopped(CTrkWksSvc *this)
{
  if ( CSvcCtrlInterface::_fStoppedOrStopping )
  {
    RaiseException(0x8DEAD012, 0, 0, 0);
    JUMPOUT(0x180004F59LL);
  }
}

```

## disassembly

```asm
0x180004f34  sub     rsp, 28h
0x180004f38  cmp     cs:?_fStoppedOrStopping@CSvcCtrlInterface@@0HA, 0; int CSvcCtrlInterface::_fStoppedOrStopping
0x180004f3f  jnz     short loc_180004F46
0x180004f41  add     rsp, 28h
0x180004f45  retn
0x180004f46  xor     r9d, r9d; lpArguments
0x180004f49  xor     r8d, r8d; nNumberOfArguments
0x180004f4c  xor     edx, edx; dwExceptionFlags
0x180004f4e  mov     ecx, 8DEAD012h; dwExceptionCode
0x180004f53  call    cs:__imp_RaiseException
```
