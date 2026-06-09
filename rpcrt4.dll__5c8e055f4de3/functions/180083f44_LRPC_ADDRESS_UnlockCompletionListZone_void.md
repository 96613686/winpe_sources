# LRPC_ADDRESS::UnlockCompletionListZone(void)

- ea: `0x180083f44`
- end: `0x180084024`
- name: `?UnlockCompletionListZone@LRPC_ADDRESS@@AEAAXXZ`
- size: `224`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f970`

## callees

- `0x180025c00`
- `0x180083f44`

## import_xrefs

- `ntdll!TpAlpcUnregisterCompletionList` at `0x180083fe1`
- `ntdll!TpAlpcUnregisterCompletionList` at `0x180083fe1`
- `ntdll!AlpcUnregisterCompletionList` at `0x180083fee`
- `ntdll!AlpcUnregisterCompletionList` at `0x180083fee`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x180083fb6`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x180083fb6`
- `ntdll!RtlAcquireResourceExclusive` at `0x180083f7d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180083f7d`
- `ntdll!RtlReleaseResource` at `0x180083fcc`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180084007`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180084007`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::UnlockCompletionListZone(LRPC_ADDRESS *this)
{
  __int64 v2; // rcx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  _InterlockedDecrement((volatile signed __int32 *)this + 84);
  if ( *((_DWORD *)this + 73) == 3 )
  {
    _InterlockedOr(v3, 0);
    if ( !*((_DWORD *)this + 84) )
    {
      if ( !RtlAcquireResourceExclusive(*((PRTL_RESOURCE *)this + 43), 1u) )
        goto LABEL_5;
      _InterlockedOr(v3, 0);
      if ( !*((_DWORD *)this + 84)
        && *((_DWORD *)this + 73) == 3
        && !(unsigned int)AlpcGetOutstandingCompletionListMessageCount(*((_QWORD *)this + 37)) )
      {
        v2 = *((_QWORD *)this + 34);
        *(_BYTE *)(v2 + 8) = 0;
        TpAlpcUnregisterCompletionList(*(_QWORD *)v2);
        if ( (int)AlpcUnregisterCompletionList(*((_QWORD *)this + 26)) < 0 )
        {
LABEL_5:
          RpcpReportFatalError(21, this);
          __debugbreak();
        }
        VirtualFree(*((LPVOID *)this + 37), 0, 0x8000u);
        *((_QWORD *)this + 37) = 0;
        *((_DWORD *)this + 73) = 0;
      }
      RtlReleaseResource(*((PRTL_RESOURCE *)this + 43));
    }
  }
}

```

## disassembly

```asm
0x180083f44  push    rbx
0x180083f46  sub     rsp, 20h
0x180083f4a  lock dec dword ptr [rcx+150h]
0x180083f51  mov     rbx, rcx
0x180083f54  mov     eax, [rcx+124h]
0x180083f5a  cmp     eax, 3
0x180083f5d  jz      short loc_180083F65
0x180083f5f  add     rsp, 20h
0x180083f63  pop     rbx
0x180083f64  retn
0x180083f65  lock or [rsp+28h+var_28], 0
0x180083f6a  mov     eax, [rcx+150h]
0x180083f70  test    eax, eax
0x180083f72  jnz     short loc_180083F5F
0x180083f74  mov     rcx, [rcx+158h]; Resource
0x180083f7b  mov     dl, 1; Wait
0x180083f7d  call    cs:__imp_RtlAcquireResourceExclusive
0x180083f83  test    al, al
0x180083f85  jnz     short loc_180083F95
0x180083f87  mov     rdx, rbx
0x180083f8a  mov     ecx, 15h
0x180083f8f  call    RpcpReportFatalError
0x180083f94  int     3; Trap to Debugger
0x180083f95  lock or [rsp+28h+var_28], 0
0x180083f9a  mov     eax, [rbx+150h]
0x180083fa0  test    eax, eax
0x180083fa2  jnz     short loc_180083FC0
0x180083fa4  mov     eax, [rbx+124h]
0x180083faa  cmp     eax, 3
0x180083fad  jnz     short loc_180083FC0
0x180083faf  mov     rcx, [rbx+128h]
0x180083fb6  call    cs:__imp_AlpcGetOutstandingCompletionListMessageCount
0x180083fbc  test    eax, eax
0x180083fbe  jz      short loc_180083FD3
0x180083fc0  mov     rcx, [rbx+158h]
0x180083fc7  add     rsp, 20h
0x180083fcb  pop     rbx
0x180083fcc  jmp     cs:__imp_RtlReleaseResource
0x180083fd3  mov     rcx, [rbx+110h]
0x180083fda  mov     byte ptr [rcx+8], 0
0x180083fde  mov     rcx, [rcx]
0x180083fe1  call    cs:__imp_TpAlpcUnregisterCompletionList
0x180083fe7  mov     rcx, [rbx+0D0h]
0x180083fee  call    cs:__imp_AlpcUnregisterCompletionList
0x180083ff4  test    eax, eax
0x180083ff6  js      short loc_180083F87
0x180083ff8  mov     rcx, [rbx+128h]; lpAddress
0x180083fff  xor     edx, edx; dwSize
0x180084001  mov     r8d, 8000h; dwFreeType
0x180084007  call    cs:__imp_VirtualFree
0x18008400d  mov     qword ptr [rbx+128h], 0
0x180084018  mov     dword ptr [rbx+124h], 0
0x180084022  jmp     short loc_180083FC0
```
