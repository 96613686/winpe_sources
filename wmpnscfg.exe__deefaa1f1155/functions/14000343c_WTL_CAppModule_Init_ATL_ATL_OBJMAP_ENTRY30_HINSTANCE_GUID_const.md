# WTL::CAppModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)

- ea: `0x14000343c`
- end: `0x1400034e5`
- name: `?Init@CAppModule@WTL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@ATL@@PEAUHINSTANCE__@@PEBU_GUID@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(WTL::CAppModule *__hidden this, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005658`

## callees

- `0x140001170`
- `0x14000343c`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003482`
- `KERNEL32!GetCurrentThreadId` at `0x140003482`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WTL::CAppModule::Init(
        WTL::CAppModule *this,
        struct ATL::_ATL_OBJMAP_ENTRY30 *a2,
        HINSTANCE a3,
        const struct _GUID *a4)
{
  unsigned int v4; // ebx
  __int64 *v5; // rdi
  __int64 *v6; // rax
  DWORD CurrentThreadId; // eax
  _QWORD *v8; // rax

  v4 = 0;
  qword_14000C328 = 0;
  v5 = off_14000C0B0[0];
  v6 = off_14000C0B8;
  while ( v5 < v6 )
  {
    if ( *v5 )
    {
      LOBYTE(this) = 1;
      (*(void (__fastcall **)(WTL::CAppModule *))(*v5 + 64))(this);
      v6 = off_14000C0B8;
    }
    ++v5;
  }
  CurrentThreadId = GetCurrentThreadId();
  try
  {
    dword_14000C330 = CurrentThreadId;
    qword_14000C338 = 0;
    v8 = operator new(0x18u);
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      *((_DWORD *)v8 + 4) = 0;
    }
    else
    {
      v8 = 0;
    }
    qword_14000C338 = v8;
  }
  catch ( ... )
  {
    v4 = 0;
    v8 = qword_14000C338;
  }
  if ( v8 )
    Block = 0;
  else
    return (unsigned int)-2147024882;
  return v4;
}

```

## disassembly

```asm
0x14000343c  mov     [rsp+arg_0], rbx
0x140003441  push    rdi
0x140003442  sub     rsp, 20h
0x140003446  xor     ebx, ebx
0x140003448  mov     cs:qword_14000C328, rbx
0x14000344f  mov     rdi, cs:off_14000C0B0
0x140003456  mov     rax, cs:off_14000C0B8
0x14000345d  jmp     short loc_14000347D
0x14000345f  mov     rdx, [rdi]
0x140003462  test    rdx, rdx
0x140003465  jz      short loc_140003479
0x140003467  mov     cl, 1
0x140003469  mov     rax, [rdx+40h]
0x14000346d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003472  mov     rax, cs:off_14000C0B8
0x140003479  add     rdi, 8
0x14000347d  cmp     rdi, rax
0x140003480  jb      short loc_14000345F
0x140003482  call    cs:__imp_GetCurrentThreadId
0x140003488  mov     cs:dword_14000C330, eax
0x14000348e  mov     cs:qword_14000C338, rbx
0x140003495  mov     ecx, 18h; Size
0x14000349a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000349f  test    rax, rax
0x1400034a2  jz      short loc_1400034B0
0x1400034a4  mov     [rax], rbx
0x1400034a7  mov     [rax+8], rbx
0x1400034ab  mov     [rax+10h], ebx
0x1400034ae  jmp     short loc_1400034B3
0x1400034b0  mov     rax, rbx
0x1400034b3  mov     cs:qword_14000C338, rax
0x1400034ba  jmp     short loc_1400034C5
0x1400034bc  xor     ebx, ebx
0x1400034be  mov     rax, cs:qword_14000C338
0x1400034c5  test    rax, rax
0x1400034c8  jnz     short loc_1400034D1
0x1400034ca  mov     ebx, 8007000Eh
0x1400034cf  jmp     short loc_1400034D8
0x1400034d1  mov     cs:Block, rbx
0x1400034d8  mov     eax, ebx
0x1400034da  mov     rbx, [rsp+28h+arg_0]
0x1400034df  add     rsp, 20h
0x1400034e3  pop     rdi
0x1400034e4  retn
```
