# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800061bc`
- end: `0x180006286`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `202`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006290`
- `0x180039540`

## callees

- `0x1800061a8`
- `0x1800061bc`
- `0x18003002c`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000624e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000624e`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005, 1u);
        JUMPOUT(0x180006285LL);
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800061bc  mov     rax, rsp
0x1800061bf  mov     [rax+8], rbx
0x1800061c3  mov     [rax+10h], rsi
0x1800061c7  mov     [rax+18h], rdi
0x1800061cb  mov     [rax+20h], r14
0x1800061cf  push    r15
0x1800061d1  sub     rsp, 20h
0x1800061d5  mov     rdi, rcx
0x1800061d8  lea     r14, [rcx+8]
0x1800061dc  cmp     dword ptr [r14], 0
0x1800061e0  jz      short loc_18000625B
0x1800061e2  cmp     qword ptr [rcx+10h], 0
0x1800061e7  jz      short loc_180006235
0x1800061e9  mov     rax, rcx
0x1800061ec  neg     rax
0x1800061ef  sbb     rsi, rsi
0x1800061f2  and     rsi, r14
0x1800061f5  jz      short loc_180006276
0x1800061f7  mov     r15, [rsi+8]
0x1800061fb  test    r15, r15
0x1800061fe  jz      short loc_180006225
0x180006200  mov     rcx, [r15+8]
0x180006204  mov     rax, [r15]
0x180006207  call    _guard_dispatch_icall
0x18000620c  mov     rbx, [r15+10h]
0x180006210  mov     edx, 18h
0x180006215  mov     rcx, r15; Block
0x180006218  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000621d  mov     r15, rbx
0x180006220  test    rbx, rbx
0x180006223  jnz     short loc_180006200
0x180006225  mov     qword ptr [rsi+8], 0
0x18000622d  mov     qword ptr [rdi+10h], 0
0x180006235  mov     rcx, [rdi+40h]
0x180006239  test    rcx, rcx
0x18000623c  jz      short loc_18000624A
0x18000623e  mov     rax, [rcx]
0x180006241  mov     rax, [rax+10h]
0x180006245  call    _guard_dispatch_icall
0x18000624a  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000624e  call    cs:__imp_DeleteCriticalSection
0x180006254  mov     dword ptr [r14], 0
0x18000625b  mov     rbx, [rsp+28h+arg_0]
0x180006260  mov     rsi, [rsp+28h+arg_8]
0x180006265  mov     rdi, [rsp+28h+arg_10]
0x18000626a  mov     r14, [rsp+28h+arg_18]
0x18000626f  add     rsp, 20h
0x180006273  pop     r15
0x180006275  retn
0x180006276  mov     edx, 1; unsigned int
0x18000627b  mov     ecx, 0C0000005h; unsigned int
0x180006280  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
