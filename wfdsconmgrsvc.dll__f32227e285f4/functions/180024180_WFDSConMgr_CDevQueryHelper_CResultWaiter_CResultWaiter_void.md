# WFDSConMgr::CDevQueryHelper::CResultWaiter::~CResultWaiter(void)

- ea: `0x180024180`
- end: `0x1800241f7`
- name: `??1CResultWaiter@CDevQueryHelper@WFDSConMgr@@UEAA@XZ`
- size: `119`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper::CResultWaiter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024300`

## callees

- `0x180024180`
- `0x18005ce24`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241de`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CDevQueryHelper::CResultWaiter::~CResultWaiter(
        WFDSConMgr::CDevQueryHelper::CResultWaiter *this)
{
  WFDSConMgr::CDevQueryHelper::CResultWaiter *v1; // rbx
  _QWORD *v2; // rdi
  const WFDSConMgr::CException *v3; // [rsp+30h] [rbp-18h] BYREF
  char *v6; // [rsp+58h] [rbp+10h]

  v1 = this;
  *(_QWORD *)this = &WFDSConMgr::CDevQueryHelper::CResultWaiter::`vftable';
  v2 = (_QWORD *)((char *)this + 160);
  v6 = (char *)this + 160;
  if ( *((_QWORD *)this + 20) )
  {
    try
    {
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(*v2, 1223);
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
      }
      v1 = this;
      v2 = v6;
    }
    catch ( const WFDSConMgr::CException *v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
          this,
          *(_DWORD *)v3);
      }
      v1 = this;
      v2 = v6;
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
      }
      v1 = this;
      v2 = v6;
    }
    *v2 = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 112));
  WFDSConMgr::SingleObjectWaiter::~SingleObjectWaiter(v1);
}

```

## disassembly

```asm
0x180024180  mov     [rsp+arg_10], rbx
0x180024185  mov     [rsp+arg_0], rcx
0x18002418a  push    rdi
0x18002418b  sub     rsp, 40h
0x18002418f  mov     rbx, rcx
0x180024192  lea     rax, ??_7CResultWaiter@CDevQueryHelper@WFDSConMgr@@6B@; const WFDSConMgr::CDevQueryHelper::CResultWaiter::`vftable'
0x180024199  mov     [rcx], rax
0x18002419c  lea     rdi, [rcx+0A0h]
0x1800241a3  mov     [rsp+48h+arg_8], rdi
0x1800241a8  cmp     qword ptr [rdi], 0
0x1800241ac  jz      short loc_1800241DA
0x1800241ae  mov     rcx, [rdi]
0x1800241b1  mov     rax, [rcx]
0x1800241b4  mov     edx, 4C7h
0x1800241b9  mov     rax, [rax+8]
0x1800241bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241c2  nop
0x1800241c3  jmp     short loc_1800241D3
0x1800241c5  jmp     short loc_1800241C9
0x1800241c7  jmp     short $+2
0x1800241c9  mov     rbx, [rsp+48h+arg_0]
0x1800241ce  mov     rdi, [rsp+48h+arg_8]
0x1800241d3  mov     qword ptr [rdi], 0
0x1800241da  lea     rcx, [rbx+70h]; lpCriticalSection
0x1800241de  call    cs:__imp_DeleteCriticalSection
0x1800241e4  nop
0x1800241e5  mov     rcx, rbx; this
0x1800241e8  mov     rbx, [rsp+48h+arg_10]
0x1800241ed  add     rsp, 40h
0x1800241f1  pop     rdi
0x1800241f2  jmp     ??1SingleObjectWaiter@WFDSConMgr@@UEAA@XZ; WFDSConMgr::SingleObjectWaiter::~SingleObjectWaiter(void)
```
