# utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(void)

- ea: `0x18000afbc`
- end: `0x18000afd2`
- name: `??1?$unique_ptr@ULAUNCH_URL_PARAMETERS@@U?$default_delete@ULAUNCH_URL_PARAMETERS@@@utl@@@utl@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b030`
- `0x18000b5dc`
- `0x1800172e4`
- `0x180017308`

## callees

- `0x18000afbc`
- `0x18000b000`

## pseudocode

```c
__int64 __fastcall utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return utl::default_delete<LAUNCH_URL_PARAMETERS>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000afbc  sub     rsp, 28h
0x18000afc0  mov     rdx, [rcx]
0x18000afc3  test    rdx, rdx
0x18000afc6  jz      short loc_18000AFCD
0x18000afc8  call    ??R?$default_delete@ULAUNCH_URL_PARAMETERS@@@utl@@QEBAXPEAULAUNCH_URL_PARAMETERS@@@Z; utl::default_delete<LAUNCH_URL_PARAMETERS>::operator()(LAUNCH_URL_PARAMETERS *)
0x18000afcd  add     rsp, 28h
0x18000afd1  retn
```
