# LRPC_ADDRESS::UnlockCompletionListZone(void)

- ea: `0x180085fe4`
- end: `0x1800860ec`
- name: `?UnlockCompletionListZone@LRPC_ADDRESS@@AEAAXXZ`
- size: `264`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020a60`

## callees

- `0x180026df0`
- `0x180085fe4`

## import_xrefs

- `ntdll!TpAlpcUnregisterCompletionList` at `0x180086093`
- `ntdll!TpAlpcUnregisterCompletionList` at `0x180086093`
- `ntdll!AlpcUnregisterCompletionList` at `0x1800860a6`
- `ntdll!AlpcUnregisterCompletionList` at `0x1800860a6`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x18008605d`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x18008605d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008601e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008601e`
- `ntdll!RtlReleaseResource` at `0x180086079`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800860c9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800860c9`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::UnlockCompletionListZone(LRPC_ADDRESS *this)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  signed __int32 v5[10]; // [rsp+0h] [rbp-28h] BYREF

  _InterlockedDecrement((volatile signed __int32 *)this + 84);
  if ( *((_DWORD *)this + 73) == 3 )
  {
    _InterlockedOr(v5, 0);
    if ( !*((_DWORD *)this + 84) )
    {
      if ( !RtlAcquireResourceExclusive(*((PRTL_RESOURCE *)this + 43), 1u) )
        goto LABEL_5;
      _InterlockedOr(v5, 0);
      if ( !*((_DWORD *)this + 84)
        && *((_DWORD *)this + 73) == 3
        && !(unsigned int)AlpcGetOutstandingCompletionListMessageCount(*((_QWORD *)this + 37)) )
      {
        v4 = *((_QWORD *)this + 34);
        *(_BYTE *)(v4 + 8) = 0;
        TpAlpcUnregisterCompletionList(*(_QWORD *)v4);
        if ( (int)AlpcUnregisterCompletionList(*((_QWORD *)this + 26)) < 0 )
        {
LABEL_5:
          RpcpReportFatalError(21, this, v2, v3);
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
0x180085fe4  push    rbx
0x180085fe6  sub     rsp, 20h
0x180085fea  lock dec dword ptr [rcx+150h]
0x180085ff1  mov     rbx, rcx
0x180085ff4  mov     eax, [rcx+124h]
0x180085ffa  cmp     eax, 3
0x180085ffd  jz      short loc_180086006
0x180085fff  add     rsp, 20h
0x180086003  pop     rbx
0x180086004  retn
0x180086006  lock or [rsp+28h+var_28], 0
0x18008600b  mov     eax, [rcx+150h]
0x180086011  test    eax, eax
0x180086013  jnz     short loc_180085FFF
0x180086015  mov     rcx, [rcx+158h]; Resource
0x18008601c  mov     dl, 1; Wait
0x18008601e  call    cs:__imp_RtlAcquireResourceExclusive
0x180086025  nop     dword ptr [rax+rax+00h]
0x18008602a  test    al, al
0x18008602c  jnz     short loc_18008603C
0x18008602e  mov     rdx, rbx
0x180086031  mov     ecx, 15h
0x180086036  call    RpcpReportFatalError
0x18008603b  int     3; Trap to Debugger
0x18008603c  lock or [rsp+28h+var_28], 0
0x180086041  mov     eax, [rbx+150h]
0x180086047  test    eax, eax
0x180086049  jnz     short loc_18008606D
0x18008604b  mov     eax, [rbx+124h]
0x180086051  cmp     eax, 3
0x180086054  jnz     short loc_18008606D
0x180086056  mov     rcx, [rbx+128h]
0x18008605d  call    cs:__imp_AlpcGetOutstandingCompletionListMessageCount
0x180086064  nop     dword ptr [rax+rax+00h]
0x180086069  test    eax, eax
0x18008606b  jz      short loc_180086085
0x18008606d  mov     rcx, [rbx+158h]
0x180086074  add     rsp, 20h
0x180086078  pop     rbx
0x180086079  jmp     cs:__imp_RtlReleaseResource
0x180086085  mov     rcx, [rbx+110h]
0x18008608c  mov     byte ptr [rcx+8], 0
0x180086090  mov     rcx, [rcx]
0x180086093  call    cs:__imp_TpAlpcUnregisterCompletionList
0x18008609a  nop     dword ptr [rax+rax+00h]
0x18008609f  mov     rcx, [rbx+0D0h]
0x1800860a6  call    cs:__imp_AlpcUnregisterCompletionList
0x1800860ad  nop     dword ptr [rax+rax+00h]
0x1800860b2  test    eax, eax
0x1800860b4  js      loc_18008602E
0x1800860ba  mov     rcx, [rbx+128h]; lpAddress
0x1800860c1  xor     edx, edx; dwSize
0x1800860c3  mov     r8d, 8000h; dwFreeType
0x1800860c9  call    cs:__imp_VirtualFree
0x1800860d0  nop     dword ptr [rax+rax+00h]
0x1800860d5  mov     qword ptr [rbx+128h], 0
0x1800860e0  mov     dword ptr [rbx+124h], 0
0x1800860ea  jmp     short loc_18008606D
```
