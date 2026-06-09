# ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)

- ea: `0x180001cd0`
- end: `0x180001d5b`
- name: `?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f78`

## callees

- `0x180001cd0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::Init(
        ATL::CComModule *this,
        struct ATL::_ATL_OBJMAP_ENTRY30 *a2,
        HINSTANCE a3,
        const struct _GUID *a4)
{
  void (__fastcall **v4)(ATL::CComModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *); // rbx
  unsigned __int64 v5; // rbx
  unsigned __int64 i; // rcx

  ATL::CAtlModule::m_libid = LIBID_MSASRXLib;
  v4 = (void (__fastcall **)(ATL::CComModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *))&off_180015000;
  if ( &off_180015000 != (_UNKNOWN *)-1LL )
  {
    qword_1800152F8 = (__int64)&off_180015000;
    if ( off_180015000 )
    {
      do
      {
        LOBYTE(this) = 1;
        v4[8](this, a2, a3, a4);
        v4 += 9;
      }
      while ( *v4 );
    }
  }
  v5 = qword_1800153C0;
  for ( i = qword_1800153C8; v5 < i; v5 += 8LL )
  {
    if ( *(_QWORD *)v5 )
    {
      LOBYTE(i) = 1;
      (*(void (__fastcall **)(unsigned __int64, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *))(*(_QWORD *)v5 + 64LL))(
        i,
        a2,
        a3,
        a4);
      i = qword_1800153C8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001cd0  push    rbx
0x180001cd2  sub     rsp, 20h
0x180001cd6  movups  xmm0, xmmword ptr cs:LIBID_MSASRXLib.Data1
0x180001cdd  movups  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x180001ce4  lea     rbx, off_180015000
0x180001ceb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001cef  jz      short loc_180001D17
0x180001cf1  mov     cs:qword_1800152F8, rbx
0x180001cf8  cmp     cs:off_180015000, 0
0x180001d00  jz      short loc_180001D17
0x180001d02  mov     cl, 1
0x180001d04  mov     rax, [rbx+40h]
0x180001d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0d  lea     rbx, [rbx+48h]
0x180001d11  cmp     qword ptr [rbx], 0
0x180001d15  jnz     short loc_180001D02
0x180001d17  mov     rbx, cs:qword_1800153C0
0x180001d1e  mov     rcx, cs:qword_1800153C8
0x180001d25  cmp     rbx, rcx
0x180001d28  jnb     short loc_180001D53
0x180001d2a  nop     word ptr [rax+rax+00h]
0x180001d30  mov     rax, [rbx]
0x180001d33  test    rax, rax
0x180001d36  jz      short loc_180001D4A
0x180001d38  mov     cl, 1
0x180001d3a  mov     rax, [rax+40h]
0x180001d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d43  mov     rcx, cs:qword_1800153C8
0x180001d4a  add     rbx, 8
0x180001d4e  cmp     rbx, rcx
0x180001d51  jb      short loc_180001D30
0x180001d53  xor     eax, eax
0x180001d55  add     rsp, 20h
0x180001d59  pop     rbx
0x180001d5a  retn
```
