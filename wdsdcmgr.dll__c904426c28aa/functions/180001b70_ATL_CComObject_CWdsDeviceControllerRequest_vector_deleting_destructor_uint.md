# ATL::CComObject<CWdsDeviceControllerRequest>::`vector deleting destructor'(uint)

- ea: `0x180001b70`
- end: `0x180001bda`
- name: `??_E?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@UEAAPEAXI@Z`
- size: `106`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001370`
- `0x180001b70`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180001ba4`
- `KERNEL32!DeleteCriticalSection` at `0x180001bb8`
- `KERNEL32!DeleteCriticalSection` at `0x180001ba4`
- `KERNEL32!DeleteCriticalSection` at `0x180001bb8`

## pseudocode

```c
char *__fastcall ATL::CComObject<CWdsDeviceControllerRequest>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWdsDeviceControllerRequest>::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  CWdsDeviceControllerRequest::Shutdown((CWdsDeviceControllerRequest *)Block);
  DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 64));
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180001b70  mov     [rsp+arg_0], rbx
0x180001b75  push    rdi
0x180001b76  sub     rsp, 20h
0x180001b7a  lea     rax, ??_7?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@6B@; const ATL::CComObject<CWdsDeviceControllerRequest>::`vftable'
0x180001b81  mov     dword ptr [rcx+8], 0C0000001h
0x180001b88  mov     [rcx], rax
0x180001b8b  mov     edi, edx
0x180001b8d  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001b94  mov     rbx, rcx
0x180001b97  lock dec dword ptr [rax+0Ch]
0x180001b9b  call    ?Shutdown@CWdsDeviceControllerRequest@@QEAAXXZ; CWdsDeviceControllerRequest::Shutdown(void)
0x180001ba0  lea     rcx, [rbx+40h]; lpCriticalSection
0x180001ba4  call    cs:__imp_DeleteCriticalSection
0x180001baa  lea     rcx, [rbx+10h]; lpCriticalSection
0x180001bae  cmp     byte ptr [rcx+28h], 0
0x180001bb2  jz      short loc_180001BBE
0x180001bb4  mov     byte ptr [rcx+28h], 0
0x180001bb8  call    cs:__imp_DeleteCriticalSection
0x180001bbe  test    dil, 1
0x180001bc2  jz      short loc_180001BCC
0x180001bc4  mov     rcx, rbx; Block
0x180001bc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001bcc  mov     rax, rbx
0x180001bcf  mov     rbx, [rsp+28h+arg_0]
0x180001bd4  add     rsp, 20h
0x180001bd8  pop     rdi
0x180001bd9  retn
```
