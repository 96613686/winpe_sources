# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180015720`
- end: `0x1800157d2`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021d80`

## callees

- `0x180015720`
- `0x1800157d8`

## import_xrefs

- `msvcrt!free` at `0x180015777`
- `msvcrt!free` at `0x1800157a6`
- `msvcrt!free` at `0x180015777`
- `msvcrt!free` at `0x1800157a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015791`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015791`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180015761`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180015761`

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
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x1800157D1LL);
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
0x180015720  mov     [rsp+arg_0], rbx
0x180015725  mov     [rsp+arg_8], rsi
0x18001572a  push    rdi
0x18001572b  sub     rsp, 20h
0x18001572f  mov     rbx, rcx
0x180015732  test    rcx, rcx
0x180015735  jz      short loc_18001579D
0x180015737  cmp     dword ptr [rcx], 48h ; 'H'
0x18001573a  jnz     short loc_18001579D
0x18001573c  mov     rsi, cs:hInstance
0x180015743  xor     edi, edi
0x180015745  cmp     [rcx+40h], edi
0x180015748  jle     short loc_18001576E
0x18001574a  test    edi, edi
0x18001574c  js      short loc_1800157CC
0x18001574e  cmp     edi, [rbx+40h]
0x180015751  jge     short loc_1800157CC
0x180015753  mov     rax, [rbx+38h]
0x180015757  mov     rdx, rsi; hInstance
0x18001575a  movsxd  rcx, edi
0x18001575d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180015761  call    cs:__imp_UnregisterClassA
0x180015767  inc     edi
0x180015769  cmp     edi, [rbx+40h]
0x18001576c  jl      short loc_18001574A
0x18001576e  mov     rcx, [rbx+38h]; Block
0x180015772  test    rcx, rcx
0x180015775  jz      short loc_180015785
0x180015777  call    cs:__imp_free
0x18001577d  mov     qword ptr [rbx+38h], 0
0x180015785  lea     rcx, [rbx+8]; lpCriticalSection
0x180015789  mov     qword ptr [rbx+40h], 0
0x180015791  call    cs:__imp_DeleteCriticalSection
0x180015797  mov     dword ptr [rbx], 0
0x18001579d  mov     rcx, [rbx+38h]; Block
0x1800157a1  test    rcx, rcx
0x1800157a4  jz      short loc_1800157B4
0x1800157a6  call    cs:__imp_free
0x1800157ac  mov     qword ptr [rbx+38h], 0
0x1800157b4  mov     rsi, [rsp+28h+arg_8]
0x1800157b9  mov     qword ptr [rbx+40h], 0
0x1800157c1  mov     rbx, [rsp+28h+arg_0]
0x1800157c6  add     rsp, 20h
0x1800157ca  pop     rdi
0x1800157cb  retn
0x1800157cc  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
