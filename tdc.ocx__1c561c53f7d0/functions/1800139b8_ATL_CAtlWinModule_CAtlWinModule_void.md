# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800139b8`
- end: `0x180013a6f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800146f0`

## callees

- `0x180009994`
- `0x1800139b8`

## import_xrefs

- `msvcrt!free` at `0x180013a0f`
- `msvcrt!free` at `0x180013a3e`
- `msvcrt!free` at `0x180013a0f`
- `msvcrt!free` at `0x180013a3e`
- `USER32!UnregisterClassA` at `0x1800139f9`
- `USER32!UnregisterClassA` at `0x1800139f9`
- `KERNEL32!DeleteCriticalSection` at `0x180013a29`
- `KERNEL32!DeleteCriticalSection` at `0x180013a29`

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
        JUMPOUT(0x180013A6ELL);
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
0x1800139b8  mov     [rsp+arg_0], rbx
0x1800139bd  mov     [rsp+arg_8], rsi
0x1800139c2  push    rdi
0x1800139c3  sub     rsp, 20h
0x1800139c7  mov     rbx, rcx
0x1800139ca  test    rcx, rcx
0x1800139cd  jz      short loc_180013A35
0x1800139cf  cmp     dword ptr [rcx], 48h ; 'H'
0x1800139d2  jnz     short loc_180013A35
0x1800139d4  mov     rsi, cs:hInstance
0x1800139db  xor     edi, edi
0x1800139dd  cmp     [rcx+40h], edi
0x1800139e0  jle     short loc_180013A06
0x1800139e2  test    edi, edi
0x1800139e4  js      short loc_180013A64
0x1800139e6  cmp     edi, [rbx+40h]
0x1800139e9  jge     short loc_180013A64
0x1800139eb  mov     rax, [rbx+38h]
0x1800139ef  mov     rdx, rsi; hInstance
0x1800139f2  movsxd  rcx, edi
0x1800139f5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800139f9  call    cs:__imp_UnregisterClassA
0x1800139ff  inc     edi
0x180013a01  cmp     edi, [rbx+40h]
0x180013a04  jl      short loc_1800139E2
0x180013a06  mov     rcx, [rbx+38h]; Block
0x180013a0a  test    rcx, rcx
0x180013a0d  jz      short loc_180013A1D
0x180013a0f  call    cs:__imp_free
0x180013a15  mov     qword ptr [rbx+38h], 0
0x180013a1d  lea     rcx, [rbx+8]; lpCriticalSection
0x180013a21  mov     qword ptr [rbx+40h], 0
0x180013a29  call    cs:__imp_DeleteCriticalSection
0x180013a2f  mov     dword ptr [rbx], 0
0x180013a35  mov     rcx, [rbx+38h]; Block
0x180013a39  test    rcx, rcx
0x180013a3c  jz      short loc_180013A4C
0x180013a3e  call    cs:__imp_free
0x180013a44  mov     qword ptr [rbx+38h], 0
0x180013a4c  mov     rsi, [rsp+28h+arg_8]
0x180013a51  mov     qword ptr [rbx+40h], 0
0x180013a59  mov     rbx, [rsp+28h+arg_0]
0x180013a5e  add     rsp, 20h
0x180013a62  pop     rdi
0x180013a63  retn
0x180013a64  mov     ecx, 0C000008Ch; unsigned int
0x180013a69  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
