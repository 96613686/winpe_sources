# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180015dbc`
- end: `0x180015e73`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f340`

## callees

- `0x180015ac8`
- `0x180015dbc`

## import_xrefs

- `msvcrt!free` at `0x180015e13`
- `msvcrt!free` at `0x180015e42`
- `msvcrt!free` at `0x180015e13`
- `msvcrt!free` at `0x180015e42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015e2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015e2d`
- `USER32!UnregisterClassA` at `0x180015dfd`
- `USER32!UnregisterClassA` at `0x180015dfd`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rsi
  int i; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180015E72LL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * i), v3);
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180015dbc  mov     [rsp+arg_0], rbx
0x180015dc1  mov     [rsp+arg_8], rsi
0x180015dc6  push    rdi
0x180015dc7  sub     rsp, 20h
0x180015dcb  mov     rbx, rcx
0x180015dce  test    rcx, rcx
0x180015dd1  jz      short loc_180015E39
0x180015dd3  cmp     dword ptr [rcx], 48h ; 'H'
0x180015dd6  jnz     short loc_180015E39
0x180015dd8  mov     rsi, cs:hInstance
0x180015ddf  xor     edi, edi
0x180015de1  cmp     [rcx+40h], edi
0x180015de4  jle     short loc_180015E0A
0x180015de6  test    edi, edi
0x180015de8  js      short loc_180015E68
0x180015dea  cmp     edi, [rbx+40h]
0x180015ded  jge     short loc_180015E68
0x180015def  mov     rax, [rbx+38h]
0x180015df3  mov     rdx, rsi; hInstance
0x180015df6  movsxd  rcx, edi
0x180015df9  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180015dfd  call    cs:__imp_UnregisterClassA
0x180015e03  inc     edi
0x180015e05  cmp     edi, [rbx+40h]
0x180015e08  jl      short loc_180015DE6
0x180015e0a  mov     rcx, [rbx+38h]; Block
0x180015e0e  test    rcx, rcx
0x180015e11  jz      short loc_180015E21
0x180015e13  call    cs:__imp_free
0x180015e19  mov     qword ptr [rbx+38h], 0
0x180015e21  lea     rcx, [rbx+8]; lpCriticalSection
0x180015e25  mov     qword ptr [rbx+40h], 0
0x180015e2d  call    cs:__imp_DeleteCriticalSection
0x180015e33  mov     dword ptr [rbx], 0
0x180015e39  mov     rcx, [rbx+38h]; Block
0x180015e3d  test    rcx, rcx
0x180015e40  jz      short loc_180015E50
0x180015e42  call    cs:__imp_free
0x180015e48  mov     qword ptr [rbx+38h], 0
0x180015e50  mov     rsi, [rsp+28h+arg_8]
0x180015e55  mov     qword ptr [rbx+40h], 0
0x180015e5d  mov     rbx, [rsp+28h+arg_0]
0x180015e62  add     rsp, 20h
0x180015e66  pop     rdi
0x180015e67  retn
0x180015e68  mov     ecx, 0C000008Ch; unsigned int
0x180015e6d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
