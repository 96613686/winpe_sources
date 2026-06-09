# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800146bc`
- end: `0x180014773`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c560`

## callees

- `0x180005b7c`
- `0x1800146bc`

## import_xrefs

- `msvcrt!free` at `0x180014713`
- `msvcrt!free` at `0x180014742`
- `msvcrt!free` at `0x180014713`
- `msvcrt!free` at `0x180014742`
- `KERNEL32!DeleteCriticalSection` at `0x18001472d`
- `KERNEL32!DeleteCriticalSection` at `0x18001472d`
- `USER32!UnregisterClassA` at `0x1800146fd`
- `USER32!UnregisterClassA` at `0x1800146fd`

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
    v3 = hModule;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180014772LL);
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
0x1800146bc  mov     [rsp+arg_0], rbx
0x1800146c1  mov     [rsp+arg_8], rsi
0x1800146c6  push    rdi
0x1800146c7  sub     rsp, 20h
0x1800146cb  mov     rbx, rcx
0x1800146ce  test    rcx, rcx
0x1800146d1  jz      short loc_180014739
0x1800146d3  cmp     dword ptr [rcx], 48h ; 'H'
0x1800146d6  jnz     short loc_180014739
0x1800146d8  mov     rsi, cs:hModule
0x1800146df  xor     edi, edi
0x1800146e1  cmp     [rcx+40h], edi
0x1800146e4  jle     short loc_18001470A
0x1800146e6  test    edi, edi
0x1800146e8  js      short loc_180014768
0x1800146ea  cmp     edi, [rbx+40h]
0x1800146ed  jge     short loc_180014768
0x1800146ef  mov     rax, [rbx+38h]
0x1800146f3  mov     rdx, rsi; hInstance
0x1800146f6  movsxd  rcx, edi
0x1800146f9  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800146fd  call    cs:__imp_UnregisterClassA
0x180014703  inc     edi
0x180014705  cmp     edi, [rbx+40h]
0x180014708  jl      short loc_1800146E6
0x18001470a  mov     rcx, [rbx+38h]; Block
0x18001470e  test    rcx, rcx
0x180014711  jz      short loc_180014721
0x180014713  call    cs:__imp_free
0x180014719  mov     qword ptr [rbx+38h], 0
0x180014721  lea     rcx, [rbx+8]; lpCriticalSection
0x180014725  mov     qword ptr [rbx+40h], 0
0x18001472d  call    cs:__imp_DeleteCriticalSection
0x180014733  mov     dword ptr [rbx], 0
0x180014739  mov     rcx, [rbx+38h]; Block
0x18001473d  test    rcx, rcx
0x180014740  jz      short loc_180014750
0x180014742  call    cs:__imp_free
0x180014748  mov     qword ptr [rbx+38h], 0
0x180014750  mov     rsi, [rsp+28h+arg_8]
0x180014755  mov     qword ptr [rbx+40h], 0
0x18001475d  mov     rbx, [rsp+28h+arg_0]
0x180014762  add     rsp, 20h
0x180014766  pop     rdi
0x180014767  retn
0x180014768  mov     ecx, 0C000008Ch; unsigned int
0x18001476d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
