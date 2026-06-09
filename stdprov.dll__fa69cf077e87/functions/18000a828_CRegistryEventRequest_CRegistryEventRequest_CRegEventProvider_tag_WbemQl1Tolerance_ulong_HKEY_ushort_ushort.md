# CRegistryEventRequest::CRegistryEventRequest(CRegEventProvider *,_tag_WbemQl1Tolerance &,ulong,HKEY__ *,ushort *,ushort *)

- ea: `0x18000a828`
- end: `0x18000a93c`
- name: `??0CRegistryEventRequest@@QEAA@PEAVCRegEventProvider@@AEAU_tag_WbemQl1Tolerance@@KPEAUHKEY__@@PEAG3@Z`
- size: `276`
- prototype: `CRegistryEventRequest *__fastcall(CRegistryEventRequest *__hidden this, struct CRegEventProvider *, struct _tag_WbemQl1Tolerance *, unsigned int, HKEY, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006740`

## callees

- `0x18000a828`
- `0x18000aa54`
- `0x180015532`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18000a886`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18000a89c`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18000a886`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18000a89c`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18000a867`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18000a867`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000a90d`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000a90d`

## pseudocode

```c
CRegistryEventRequest *__fastcall CRegistryEventRequest::CRegistryEventRequest(
        CRegistryEventRequest *this,
        struct CRegEventProvider *a2,
        struct _tag_WbemQl1Tolerance *a3,
        unsigned int a4,
        HKEY a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  unsigned __int64 v7; // rsi
  int v10; // eax
  char pExceptionObject; // [rsp+48h] [rbp+20h] BYREF

  v7 = a4;
  *(_QWORD *)this = &CRegistryEventRequest::`vftable';
  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 2) = a2;
  CFlexArray::CFlexArray((CRegistryEventRequest *)((char *)this + 32), 8, 100);
  *((_QWORD *)this + 15) = a5;
  WString::WString((CRegistryEventRequest *)((char *)this + 128), a6, 0);
  WString::WString((CRegistryEventRequest *)((char *)this + 136), a7, 0);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 1;
  *((_QWORD *)this + 22) = 0;
  CCritSec::CCritSec((CRegistryEventRequest *)((char *)this + 184));
  if ( *(_BYTE *)a3 )
    v10 = 0;
  else
    v10 = (int)(*((double *)a3 + 1) * 1000.0);
  *((_DWORD *)this + 6) = v10;
  if ( CFlexArray::InsertAt((CRegistryEventRequest *)((char *)this + 32), *((_DWORD *)this + 8), (void *)v7) )
    throw (CX_MemoryException *)&pExceptionObject;
  return this;
}

```

## disassembly

```asm
0x18000a828  mov     [rsp+arg_8], rbx
0x18000a82d  mov     [rsp+arg_10], rsi
0x18000a832  mov     [rsp+arg_0], rcx
0x18000a837  push    rdi
0x18000a838  sub     rsp, 20h
0x18000a83c  mov     esi, r9d
0x18000a83f  mov     rdi, r8
0x18000a842  mov     rbx, rcx
0x18000a845  lea     rax, ??_7CRegistryEventRequest@@6B@; const CRegistryEventRequest::`vftable'
0x18000a84c  mov     [rcx], rax
0x18000a84f  mov     dword ptr [rcx+8], 1
0x18000a856  mov     [rcx+10h], rdx
0x18000a85a  add     rcx, 20h ; ' '
0x18000a85e  mov     edx, 8
0x18000a863  lea     r8d, [rdx+5Ch]
0x18000a867  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18000a86d  nop
0x18000a86e  mov     rax, [rsp+28h+arg_20]
0x18000a873  mov     [rbx+78h], rax
0x18000a877  lea     rcx, [rbx+80h]
0x18000a87e  xor     r8d, r8d
0x18000a881  mov     rdx, [rsp+28h+arg_28]
0x18000a886  call    cs:__imp_??0WString@@QEAA@PEAGH@Z; WString::WString(ushort *,int)
0x18000a88c  nop
0x18000a88d  lea     rcx, [rbx+88h]
0x18000a894  xor     r8d, r8d
0x18000a897  mov     rdx, [rsp+28h+arg_30]
0x18000a89c  call    cs:__imp_??0WString@@QEAA@PEAGH@Z; WString::WString(ushort *,int)
0x18000a8a2  nop
0x18000a8a3  mov     qword ptr [rbx+90h], 0
0x18000a8ae  mov     qword ptr [rbx+98h], 0
0x18000a8b9  mov     qword ptr [rbx+0A0h], 0
0x18000a8c4  mov     dword ptr [rbx+0A8h], 1
0x18000a8ce  mov     qword ptr [rbx+0B0h], 0
0x18000a8d9  lea     rcx, [rbx+0B8h]; this
0x18000a8e0  call    ??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18000a8e5  nop
0x18000a8e6  cmp     byte ptr [rdi], 0
0x18000a8e9  jz      short loc_18000A8EF
0x18000a8eb  xor     eax, eax
0x18000a8ed  jmp     short loc_18000A901
0x18000a8ef  movsd   xmm0, qword ptr [rdi+8]
0x18000a8f4  mulsd   xmm0, cs:__real@408f400000000000
0x18000a8fc  cvttsd2si rax, xmm0
0x18000a901  mov     [rbx+18h], eax
0x18000a904  lea     rcx, [rbx+20h]
0x18000a908  mov     r8, rsi
0x18000a90b  mov     edx, [rcx]
0x18000a90d  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18000a913  test    eax, eax
0x18000a915  jz      short loc_18000A929
0x18000a917  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000a91e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000a923  call    _CxxThrowException_0
0x18000a929  mov     rax, rbx
0x18000a92c  mov     rbx, [rsp+28h+arg_8]
0x18000a931  mov     rsi, [rsp+28h+arg_10]
0x18000a936  add     rsp, 20h
0x18000a93a  pop     rdi
0x18000a93b  retn
```
