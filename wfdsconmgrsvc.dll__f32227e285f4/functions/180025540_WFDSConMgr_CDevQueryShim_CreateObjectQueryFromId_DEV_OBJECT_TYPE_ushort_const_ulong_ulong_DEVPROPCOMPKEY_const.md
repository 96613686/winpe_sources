# WFDSConMgr::CDevQueryShim::CreateObjectQueryFromId(_DEV_OBJECT_TYPE,ushort const *,ulong,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,HDEVQUERY__ * *)

- ea: `0x180025540`
- end: `0x1800255cc`
- name: `?CreateObjectQueryFromId@CDevQueryShim@WFDSConMgr@@UEAAJW4_DEV_OBJECT_TYPE@@PEBGKKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@P6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z6PEAPEAU7@@Z`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryFromIdEx` at `0x1800255c0`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryFromIdEx` at `0x1800255c0`

## pseudocode

```c
__int64 __fastcall WFDSConMgr::CDevQueryShim::CreateObjectQueryFromId(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  return DevCreateObjectQueryFromIdEx(a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13);
}

```

## disassembly

```asm
0x180025540  push    rbx
0x180025542  sub     rsp, 60h
0x180025546  mov     rax, [rsp+68h+arg_60]
0x18002554e  mov     r10d, r9d
0x180025551  mov     r9d, [rsp+68h+arg_20]
0x180025559  mov     r11, r8
0x18002555c  mov     [rsp+68h+var_10], rax
0x180025561  mov     ecx, edx
0x180025563  mov     rax, [rsp+68h+arg_58]
0x18002556b  mov     r8d, r10d
0x18002556e  mov     [rsp+68h+var_18], rax
0x180025573  mov     rdx, r11
0x180025576  mov     rax, [rsp+68h+arg_50]
0x18002557e  mov     [rsp+68h+var_20], rax
0x180025583  mov     rax, [rsp+68h+arg_48]
0x18002558b  mov     [rsp+68h+var_28], rax
0x180025590  mov     eax, [rsp+68h+arg_40]
0x180025597  mov     [rsp+68h+var_30], eax
0x18002559b  mov     rax, [rsp+68h+arg_38]
0x1800255a3  mov     [rsp+68h+var_38], rax
0x1800255a8  mov     eax, [rsp+68h+arg_30]
0x1800255af  mov     [rsp+68h+var_40], eax
0x1800255b3  mov     rax, [rsp+68h+arg_28]
0x1800255bb  mov     [rsp+68h+var_48], rax
0x1800255c0  call    cs:__imp_DevCreateObjectQueryFromIdEx
0x1800255c6  add     rsp, 60h
0x1800255ca  pop     rbx
0x1800255cb  retn
```
