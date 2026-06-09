# ATL::CComAggObject<CRecoExt>::`scalar deleting destructor'(uint)

- ea: `0x1800015f0`
- end: `0x180001658`
- name: `??_G?$CComAggObject@VCRecoExt@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001560`

## callees

- `0x1800015f0`
- `0x180002594`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001631`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001631`

## pseudocode

```c
char *__fastcall ATL::CComAggObject<CRecoExt>::`scalar deleting destructor'(char *a1, char a2)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CRecoExt>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( a1[136] )
  {
    a1[136] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1, 0xA0u);
  return a1;
}

```

## disassembly

```asm
0x1800015f0  mov     [rsp+arg_0], rbx
0x1800015f5  push    rdi
0x1800015f6  sub     rsp, 20h
0x1800015fa  mov     dword ptr [rcx+8], 0C0000001h
0x180001601  lea     rax, ??_7?$CComAggObject@VCRecoExt@@@ATL@@6B@; const ATL::CComAggObject<CRecoExt>::`vftable'
0x180001608  mov     [rcx], rax
0x18000160b  mov     rbx, rcx
0x18000160e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001615  mov     edi, edx
0x180001617  mov     rax, [rcx]
0x18000161a  mov     rax, [rax+10h]
0x18000161e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001623  lea     rcx, [rbx+60h]; lpCriticalSection
0x180001627  cmp     byte ptr [rcx+28h], 0
0x18000162b  jz      short loc_180001637
0x18000162d  mov     byte ptr [rcx+28h], 0
0x180001631  call    cs:__imp_DeleteCriticalSection
0x180001637  test    dil, 1
0x18000163b  jz      short loc_18000164A
0x18000163d  mov     edx, 0A0h; unsigned __int64
0x180001642  mov     rcx, rbx; void *
0x180001645  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000164a  mov     rax, rbx
0x18000164d  mov     rbx, [rsp+28h+arg_0]
0x180001652  add     rsp, 20h
0x180001656  pop     rdi
0x180001657  retn
```
