# CService::CB_HandlerEx(ulong,ulong,void *,void *)

- ea: `0x180005ea0`
- end: `0x180005f1d`
- name: `?CB_HandlerEx@CService@@CAKKKPEAX0@Z`
- size: `125`
- prototype: `DWORD __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea0`
- `0x180005f30`
- `0x180010010`

## pseudocode

```c
DWORD __fastcall CService::CB_HandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD result; // eax
  DWORD v6; // edi
  void (__fastcall **v7)(LPVOID, __int64); // rcx

  if ( !lpContext || *((_DWORD *)lpContext + 4) != 1129730883 )
    return _GetDefaultControlRet(dwControl);
  _InterlockedIncrement((volatile signed __int32 *)lpContext + 2);
  result = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID))(*(_QWORD *)lpContext + 16LL))(
             lpContext,
             dwControl,
             lpEventData);
  v6 = result;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpContext + 2, 0xFFFFFFFF) == 1 )
  {
    v7 = *(void (__fastcall ***)(LPVOID, __int64))lpContext;
    *((_BYTE *)lpContext + 12) = 1;
    (*v7)(lpContext, 1);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180005ea0  push    rbx
0x180005ea2  sub     rsp, 20h
0x180005ea6  mov     rbx, r9
0x180005ea9  test    r9, r9
0x180005eac  jz      short loc_180005EB8
0x180005eae  cmp     dword ptr [r9+10h], 43565343h
0x180005eb6  jz      short loc_180005EC2
0x180005eb8  add     rsp, 20h
0x180005ebc  pop     rbx
0x180005ebd  jmp     ?_GetDefaultControlRet@@YAKK@Z; _GetDefaultControlRet(ulong)
0x180005ec2  mov     [rsp+28h+arg_0], rdi
0x180005ec7  lock inc dword ptr [r9+8]
0x180005ecc  mov     rax, [r9]
0x180005ecf  mov     edx, ecx
0x180005ed1  mov     rcx, rbx
0x180005ed4  mov     rax, [rax+10h]
0x180005ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005edd  mov     edi, eax
0x180005edf  mov     ecx, 0FFFFFFFFh
0x180005ee4  lock xadd [rbx+8], ecx
0x180005ee9  cmp     ecx, 1
0x180005eec  jz      short loc_180005EF9
0x180005eee  mov     rdi, [rsp+28h+arg_0]
0x180005ef3  add     rsp, 20h
0x180005ef7  pop     rbx
0x180005ef8  retn
0x180005ef9  mov     rcx, [rbx]
0x180005efc  mov     edx, 1
0x180005f01  mov     byte ptr [rbx+0Ch], 1
0x180005f05  mov     rax, [rcx]
0x180005f08  mov     rcx, rbx
0x180005f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f10  mov     eax, edi
0x180005f12  mov     rdi, [rsp+28h+arg_0]
0x180005f17  add     rsp, 20h
0x180005f1b  pop     rbx
0x180005f1c  retn
```
