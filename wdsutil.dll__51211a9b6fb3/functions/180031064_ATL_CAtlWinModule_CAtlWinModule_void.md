# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180031064`
- end: `0x180031140`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `220`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180033ef0`

## callees

- `0x180008204`
- `0x180031064`

## import_xrefs

- `msvcrt!free` at `0x1800310cd`
- `msvcrt!free` at `0x180031108`
- `msvcrt!free` at `0x1800310cd`
- `msvcrt!free` at `0x180031108`
- `KERNEL32!DeleteCriticalSection` at `0x1800310ed`
- `KERNEL32!DeleteCriticalSection` at `0x1800310ed`
- `USER32!UnregisterClassA` at `0x1800310b1`
- `USER32!UnregisterClassA` at `0x1800310b1`

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
        JUMPOUT(0x18003113FLL);
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
0x180031064  mov     [rsp+arg_0], rbx
0x180031069  mov     [rsp+arg_8], rsi
0x18003106e  push    rdi
0x18003106f  sub     rsp, 20h
0x180031073  mov     rbx, rcx
0x180031076  test    rcx, rcx
0x180031079  jz      loc_1800310FF
0x18003107f  cmp     dword ptr [rcx], 48h ; 'H'
0x180031082  jnz     short loc_1800310FF
0x180031084  mov     rsi, cs:hInstance
0x18003108b  xor     edi, edi
0x18003108d  cmp     [rcx+40h], edi
0x180031090  jle     short loc_1800310C4
0x180031092  test    edi, edi
0x180031094  js      loc_180031135
0x18003109a  cmp     edi, [rbx+40h]
0x18003109d  jge     loc_180031135
0x1800310a3  mov     rax, [rbx+38h]
0x1800310a7  mov     rdx, rsi; hInstance
0x1800310aa  movsxd  rcx, edi
0x1800310ad  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800310b1  call    cs:__imp_UnregisterClassA
0x1800310b8  nop     dword ptr [rax+rax+00h]
0x1800310bd  inc     edi
0x1800310bf  cmp     edi, [rbx+40h]
0x1800310c2  jl      short loc_180031092
0x1800310c4  mov     rcx, [rbx+38h]; Block
0x1800310c8  test    rcx, rcx
0x1800310cb  jz      short loc_1800310E1
0x1800310cd  call    cs:__imp_free
0x1800310d4  nop     dword ptr [rax+rax+00h]
0x1800310d9  mov     qword ptr [rbx+38h], 0
0x1800310e1  lea     rcx, [rbx+8]; lpCriticalSection
0x1800310e5  mov     qword ptr [rbx+40h], 0
0x1800310ed  call    cs:__imp_DeleteCriticalSection
0x1800310f4  nop     dword ptr [rax+rax+00h]
0x1800310f9  mov     dword ptr [rbx], 0
0x1800310ff  mov     rcx, [rbx+38h]; Block
0x180031103  test    rcx, rcx
0x180031106  jz      short loc_18003111C
0x180031108  call    cs:__imp_free
0x18003110f  nop     dword ptr [rax+rax+00h]
0x180031114  mov     qword ptr [rbx+38h], 0
0x18003111c  mov     rsi, [rsp+28h+arg_8]
0x180031121  mov     qword ptr [rbx+40h], 0
0x180031129  mov     rbx, [rsp+28h+arg_0]
0x18003112e  add     rsp, 20h
0x180031132  pop     rdi
0x180031133  retn
0x180031135  mov     ecx, 0C000008Ch; unsigned int
0x18003113a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
