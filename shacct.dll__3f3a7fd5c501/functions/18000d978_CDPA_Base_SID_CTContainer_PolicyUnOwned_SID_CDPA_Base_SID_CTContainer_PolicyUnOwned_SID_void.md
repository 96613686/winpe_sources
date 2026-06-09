# CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::~CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>(void)

- ea: `0x18000d978`
- end: `0x18000d98c`
- name: `??1?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d994`
- `0x18000d9f8`
- `0x180014268`
- `0x1800142a0`

## callees

- `0x18000d978`
- `0x18000dd44`

## pseudocode

```c
__int64 __fastcall CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::~CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return CDPA_Base<_WTS_SESSION_INFOW,CTContainer_PolicyUnOwned<_WTS_SESSION_INFOW>>::Destroy();
  return result;
}

```

## disassembly

```asm
0x18000d978  sub     rsp, 28h
0x18000d97c  cmp     qword ptr [rcx], 0
0x18000d980  jz      short loc_18000D987
0x18000d982  call    ?Destroy@?$CDPA_Base@U_WTS_SESSION_INFOW@@V?$CTContainer_PolicyUnOwned@U_WTS_SESSION_INFOW@@@@@@QEAAHXZ; CDPA_Base<_WTS_SESSION_INFOW,CTContainer_PolicyUnOwned<_WTS_SESSION_INFOW>>::Destroy(void)
0x18000d987  add     rsp, 28h
0x18000d98b  retn
```
