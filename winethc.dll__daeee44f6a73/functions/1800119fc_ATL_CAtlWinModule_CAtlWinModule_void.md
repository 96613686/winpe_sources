# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800119fc`
- end: `0x180011ad8`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `220`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800132e0`

## callees

- `0x18000d798`
- `0x1800119fc`

## import_xrefs

- `msvcrt!free` at `0x180011a65`
- `msvcrt!free` at `0x180011aa0`
- `msvcrt!free` at `0x180011a65`
- `msvcrt!free` at `0x180011aa0`
- `KERNEL32!DeleteCriticalSection` at `0x180011a85`
- `KERNEL32!DeleteCriticalSection` at `0x180011a85`
- `USER32!UnregisterClassA` at `0x180011a49`
- `USER32!UnregisterClassA` at `0x180011a49`

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
        JUMPOUT(0x180011AD7LL);
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
0x1800119fc  mov     [rsp+arg_0], rbx
0x180011a01  mov     [rsp+arg_8], rsi
0x180011a06  push    rdi
0x180011a07  sub     rsp, 20h
0x180011a0b  mov     rbx, rcx
0x180011a0e  test    rcx, rcx
0x180011a11  jz      loc_180011A97
0x180011a17  cmp     dword ptr [rcx], 48h ; 'H'
0x180011a1a  jnz     short loc_180011A97
0x180011a1c  mov     rsi, cs:hModule
0x180011a23  xor     edi, edi
0x180011a25  cmp     [rcx+40h], edi
0x180011a28  jle     short loc_180011A5C
0x180011a2a  test    edi, edi
0x180011a2c  js      loc_180011ACD
0x180011a32  cmp     edi, [rbx+40h]
0x180011a35  jge     loc_180011ACD
0x180011a3b  mov     rax, [rbx+38h]
0x180011a3f  mov     rdx, rsi; hInstance
0x180011a42  movsxd  rcx, edi
0x180011a45  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180011a49  call    cs:__imp_UnregisterClassA
0x180011a50  nop     dword ptr [rax+rax+00h]
0x180011a55  inc     edi
0x180011a57  cmp     edi, [rbx+40h]
0x180011a5a  jl      short loc_180011A2A
0x180011a5c  mov     rcx, [rbx+38h]; Block
0x180011a60  test    rcx, rcx
0x180011a63  jz      short loc_180011A79
0x180011a65  call    cs:__imp_free
0x180011a6c  nop     dword ptr [rax+rax+00h]
0x180011a71  mov     qword ptr [rbx+38h], 0
0x180011a79  lea     rcx, [rbx+8]; lpCriticalSection
0x180011a7d  mov     qword ptr [rbx+40h], 0
0x180011a85  call    cs:__imp_DeleteCriticalSection
0x180011a8c  nop     dword ptr [rax+rax+00h]
0x180011a91  mov     dword ptr [rbx], 0
0x180011a97  mov     rcx, [rbx+38h]; Block
0x180011a9b  test    rcx, rcx
0x180011a9e  jz      short loc_180011AB4
0x180011aa0  call    cs:__imp_free
0x180011aa7  nop     dword ptr [rax+rax+00h]
0x180011aac  mov     qword ptr [rbx+38h], 0
0x180011ab4  mov     rsi, [rsp+28h+arg_8]
0x180011ab9  mov     qword ptr [rbx+40h], 0
0x180011ac1  mov     rbx, [rsp+28h+arg_0]
0x180011ac6  add     rsp, 20h
0x180011aca  pop     rdi
0x180011acb  retn
0x180011acd  mov     ecx, 0C000008Ch; unsigned int
0x180011ad2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
