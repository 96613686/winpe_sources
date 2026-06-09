# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180008b98`
- end: `0x180008c75`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `221`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ce40`

## callees

- `0x180002634`
- `0x180005404`
- `0x180008b98`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008c24`
- `KERNEL32!DeleteCriticalSection` at `0x180008c24`
- `USER32!UnregisterClassA` at `0x180008beb`
- `USER32!UnregisterClassA` at `0x180008beb`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v2; // rbp
  int v4; // edi
  __int64 v5; // rsi
  void *v6; // rcx
  void *v7; // rcx

  v2 = hInstance;
  if ( this && *(_DWORD *)this == 72 )
  {
    v4 = 0;
    if ( *((int *)this + 16) > 0 )
    {
      v5 = 0;
      do
      {
        if ( v5 < 0 || v4 >= *((_DWORD *)this + 16) )
        {
          ATL::_AtlRaiseException(0xC000008C, a2);
          JUMPOUT(0x180008C74LL);
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(v5 + *((_QWORD *)this + 7)), v2);
        ++v4;
        v5 += 2;
      }
      while ( v4 < *((_DWORD *)this + 16) );
    }
    v6 = (void *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      free(v6);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v7 = (void *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    free(v7);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180008b98  mov     [rsp+arg_0], rbx
0x180008b9d  mov     [rsp+arg_8], rbp
0x180008ba2  mov     [rsp+arg_10], rsi
0x180008ba7  push    rdi
0x180008ba8  sub     rsp, 20h
0x180008bac  mov     rbp, cs:hInstance
0x180008bb3  mov     rbx, rcx
0x180008bb6  test    rcx, rcx
0x180008bb9  jz      short loc_180008C36
0x180008bbb  cmp     dword ptr [rcx], 0
0x180008bbe  jz      short loc_180008C36
0x180008bc0  cmp     dword ptr [rcx], 48h ; 'H'
0x180008bc3  jnz     short loc_180008C36
0x180008bc5  xor     edi, edi
0x180008bc7  cmp     [rcx+40h], edi
0x180008bca  jle     short loc_180008C02
0x180008bcc  xor     esi, esi
0x180008bce  test    rsi, rsi
0x180008bd1  js      loc_180008C6A
0x180008bd7  cmp     edi, [rbx+40h]
0x180008bda  jge     loc_180008C6A
0x180008be0  mov     rax, [rbx+38h]
0x180008be4  mov     rdx, rbp; hInstance
0x180008be7  movzx   ecx, word ptr [rsi+rax]; lpClassName
0x180008beb  call    cs:__imp_UnregisterClassA
0x180008bf2  nop     dword ptr [rax+rax+00h]
0x180008bf7  inc     edi
0x180008bf9  add     rsi, 2
0x180008bfd  cmp     edi, [rbx+40h]
0x180008c00  jl      short loc_180008BCE
0x180008c02  mov     rcx, [rbx+38h]; Block
0x180008c06  test    rcx, rcx
0x180008c09  jz      short loc_180008C18
0x180008c0b  call    free
0x180008c10  mov     qword ptr [rbx+38h], 0
0x180008c18  lea     rcx, [rbx+8]; lpCriticalSection
0x180008c1c  mov     qword ptr [rbx+40h], 0
0x180008c24  call    cs:__imp_DeleteCriticalSection
0x180008c2b  nop     dword ptr [rax+rax+00h]
0x180008c30  mov     dword ptr [rbx], 0
0x180008c36  mov     rcx, [rbx+38h]; Block
0x180008c3a  test    rcx, rcx
0x180008c3d  jz      short loc_180008C4C
0x180008c3f  call    free
0x180008c44  mov     qword ptr [rbx+38h], 0
0x180008c4c  mov     rbp, [rsp+28h+arg_8]
0x180008c51  mov     rsi, [rsp+28h+arg_10]
0x180008c56  mov     qword ptr [rbx+40h], 0
0x180008c5e  mov     rbx, [rsp+28h+arg_0]
0x180008c63  add     rsp, 20h
0x180008c67  pop     rdi
0x180008c68  retn
0x180008c6a  mov     ecx, 0C000008Ch; unsigned int
0x180008c6f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
