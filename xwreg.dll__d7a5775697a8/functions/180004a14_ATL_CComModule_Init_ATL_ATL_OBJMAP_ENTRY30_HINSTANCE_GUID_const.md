# ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)

- ea: `0x180004a14`
- end: `0x180004a88`
- name: `?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001160`

## callees

- `0x180004a14`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::Init(
        ATL::CComModule *this,
        struct ATL::_ATL_OBJMAP_ENTRY30 *a2,
        HINSTANCE a3,
        const struct _GUID *a4)
{
  void (__fastcall **v4)(ATL::CComModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *); // rbx
  __int64 *v5; // rbx
  __int64 *v6; // rax

  v4 = (void (__fastcall **)(ATL::CComModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *))&off_18001D020;
  if ( &off_18001D020 != (_UNKNOWN *)-1LL )
  {
    qword_18001E3A8 = (__int64)&off_18001D020;
    if ( off_18001D020 )
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
  v5 = off_18001D330[0];
  v6 = off_18001D338;
  while ( v5 < v6 )
  {
    if ( *v5 )
    {
      LOBYTE(this) = 1;
      (*(void (__fastcall **)(ATL::CComModule *))(*v5 + 64))(this);
      v6 = off_18001D338;
    }
    ++v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180004a14  push    rbx
0x180004a16  sub     rsp, 20h
0x180004a1a  lea     rbx, off_18001D020
0x180004a21  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180004a25  jz      short loc_180004A4D
0x180004a27  mov     cs:qword_18001E3A8, rbx
0x180004a2e  cmp     cs:off_18001D020, 0
0x180004a36  jz      short loc_180004A4D
0x180004a38  mov     cl, 1
0x180004a3a  mov     rax, [rbx+40h]
0x180004a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a43  lea     rbx, [rbx+48h]
0x180004a47  cmp     qword ptr [rbx], 0
0x180004a4b  jnz     short loc_180004A38
0x180004a4d  mov     rbx, cs:off_18001D330
0x180004a54  mov     rax, cs:off_18001D338
0x180004a5b  jmp     short loc_180004A7B
0x180004a5d  mov     rdx, [rbx]
0x180004a60  test    rdx, rdx
0x180004a63  jz      short loc_180004A77
0x180004a65  mov     cl, 1
0x180004a67  mov     rax, [rdx+40h]
0x180004a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a70  mov     rax, cs:off_18001D338
0x180004a77  add     rbx, 8
0x180004a7b  cmp     rbx, rax
0x180004a7e  jb      short loc_180004A5D
0x180004a80  xor     eax, eax
0x180004a82  add     rsp, 20h
0x180004a86  pop     rbx
0x180004a87  retn
```
