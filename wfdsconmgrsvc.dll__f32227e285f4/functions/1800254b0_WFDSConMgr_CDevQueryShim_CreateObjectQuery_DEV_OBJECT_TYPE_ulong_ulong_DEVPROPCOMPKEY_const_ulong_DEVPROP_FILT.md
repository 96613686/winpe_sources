# WFDSConMgr::CDevQueryShim::CreateObjectQuery(_DEV_OBJECT_TYPE,ulong,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,HDEVQUERY__ * *)

- ea: `0x1800254b0`
- end: `0x18002552f`
- name: `?CreateObjectQuery@CDevQueryShim@WFDSConMgr@@UEAAJW4_DEV_OBJECT_TYPE@@KKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@P6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z5PEAPEAU7@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180025523`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180025523`

## pseudocode

```c
__int64 __fastcall WFDSConMgr::CDevQueryShim::CreateObjectQuery(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  return DevCreateObjectQueryEx(a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12);
}

```

## disassembly

```asm
0x1800254b0  push    rbx
0x1800254b2  sub     rsp, 60h
0x1800254b6  mov     rax, [rsp+68h+arg_58]
0x1800254be  mov     r10d, r9d
0x1800254c1  mov     r9, [rsp+68h+arg_20]
0x1800254c9  mov     r11d, r8d
0x1800254cc  mov     [rsp+68h+var_18], rax
0x1800254d1  mov     ecx, edx
0x1800254d3  mov     rax, [rsp+68h+arg_50]
0x1800254db  mov     r8d, r10d
0x1800254de  mov     [rsp+68h+var_20], rax
0x1800254e3  mov     edx, r11d
0x1800254e6  mov     rax, [rsp+68h+arg_48]
0x1800254ee  mov     [rsp+68h+var_28], rax
0x1800254f3  mov     rax, [rsp+68h+arg_40]
0x1800254fb  mov     [rsp+68h+var_30], rax
0x180025500  mov     eax, [rsp+68h+arg_38]
0x180025507  mov     [rsp+68h+var_38], eax
0x18002550b  mov     rax, [rsp+68h+arg_30]
0x180025513  mov     [rsp+68h+var_40], rax
0x180025518  mov     eax, [rsp+68h+arg_28]
0x18002551f  mov     [rsp+68h+var_48], eax
0x180025523  call    cs:__imp_DevCreateObjectQueryEx
0x180025529  add     rsp, 60h
0x18002552d  pop     rbx
0x18002552e  retn
```
