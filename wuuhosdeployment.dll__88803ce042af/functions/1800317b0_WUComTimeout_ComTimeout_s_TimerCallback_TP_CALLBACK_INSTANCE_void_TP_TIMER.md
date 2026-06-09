# WUComTimeout::ComTimeout::s_TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800317b0`
- end: `0x1800317fb`
- name: `?s_TimerCallback@ComTimeout@WUComTimeout@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `75`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000956c`
- `0x1800317b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x1800317c2`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x1800317c2`

## string_xrefs

- `0x1800317ce`: `ComTimeout::s_TimerCallback was not able to cancel the COM call`

## pseudocode

```c
void __fastcall WUComTimeout::ComTimeout::s_TimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  if ( Context )
  {
    if ( CoCancelCall(*((_DWORD *)Context + 2), 0) >= 0 )
      *((_BYTE *)Context + 13) = 1;
    else
      WUTrace(0, 0, 0x10000, 1);
  }
}

```

## disassembly

```asm
0x1800317b0  test    rdx, rdx
0x1800317b3  jz      short locret_1800317FA
0x1800317b5  push    rbx
0x1800317b6  sub     rsp, 30h
0x1800317ba  mov     rbx, rdx
0x1800317bd  xor     edx, edx; ulTimeout
0x1800317bf  mov     ecx, [rbx+8]; dwThreadId
0x1800317c2  call    cs:__imp_CoCancelCall
0x1800317c8  test    eax, eax
0x1800317ca  jns     short loc_1800317F1
0x1800317cc  xor     edx, edx
0x1800317ce  lea     rcx, aComtimeoutSTim; "ComTimeout::s_TimerCallback was not abl"...
0x1800317d5  mov     [rsp+38h+var_10], rcx
0x1800317da  mov     r8d, 10000h
0x1800317e0  xor     ecx, ecx
0x1800317e2  mov     [rsp+38h+var_18], eax
0x1800317e6  lea     r9d, [rdx+1]
0x1800317ea  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800317ef  jmp     short loc_1800317F5
0x1800317f1  mov     byte ptr [rbx+0Dh], 1
0x1800317f5  add     rsp, 30h
0x1800317f9  pop     rbx
0x1800317fa  retn
```
