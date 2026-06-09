# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x140006140`
- end: `0x1400061f5`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007830`

## callees

- `0x140001e76`
- `0x14000539c`
- `0x140006140`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400061b0`
- `KERNEL32!DeleteCriticalSection` at `0x1400061b0`
- `USER32!UnregisterClassA` at `0x140006181`
- `USER32!UnregisterClassA` at `0x140006181`

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
        JUMPOUT(0x1400061F4LL);
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
0x140006140  mov     [rsp+arg_0], rbx
0x140006145  mov     [rsp+arg_8], rsi
0x14000614a  push    rdi
0x14000614b  sub     rsp, 20h
0x14000614f  mov     rbx, rcx
0x140006152  test    rcx, rcx
0x140006155  jz      short loc_1400061BC
0x140006157  cmp     dword ptr [rcx], 48h ; 'H'
0x14000615a  jnz     short loc_1400061BC
0x14000615c  mov     rsi, cs:hInstance
0x140006163  xor     edi, edi
0x140006165  cmp     [rcx+40h], edi
0x140006168  jle     short loc_14000618E
0x14000616a  test    edi, edi
0x14000616c  js      short loc_1400061EA
0x14000616e  cmp     edi, [rbx+40h]
0x140006171  jge     short loc_1400061EA
0x140006173  mov     rax, [rbx+38h]
0x140006177  mov     rdx, rsi; hInstance
0x14000617a  movsxd  rcx, edi
0x14000617d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x140006181  call    cs:__imp_UnregisterClassA
0x140006187  inc     edi
0x140006189  cmp     edi, [rbx+40h]
0x14000618c  jl      short loc_14000616A
0x14000618e  mov     rcx, [rbx+38h]; Block
0x140006192  test    rcx, rcx
0x140006195  jz      short loc_1400061A4
0x140006197  call    free
0x14000619c  mov     qword ptr [rbx+38h], 0
0x1400061a4  lea     rcx, [rbx+8]; lpCriticalSection
0x1400061a8  mov     qword ptr [rbx+40h], 0
0x1400061b0  call    cs:__imp_DeleteCriticalSection
0x1400061b6  mov     dword ptr [rbx], 0
0x1400061bc  mov     rcx, [rbx+38h]; Block
0x1400061c0  test    rcx, rcx
0x1400061c3  jz      short loc_1400061D2
0x1400061c5  call    free
0x1400061ca  mov     qword ptr [rbx+38h], 0
0x1400061d2  mov     rsi, [rsp+28h+arg_8]
0x1400061d7  mov     qword ptr [rbx+40h], 0
0x1400061df  mov     rbx, [rsp+28h+arg_0]
0x1400061e4  add     rsp, 20h
0x1400061e8  pop     rdi
0x1400061e9  retn
0x1400061ea  mov     ecx, 0C000008Ch; unsigned int
0x1400061ef  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
