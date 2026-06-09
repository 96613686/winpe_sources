# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000d1fc`
- end: `0x18000d2ae`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015c60`

## callees

- `0x18000d1fc`
- `0x18000d2b4`

## import_xrefs

- `msvcrt!free` at `0x18000d253`
- `msvcrt!free` at `0x18000d282`
- `msvcrt!free` at `0x18000d253`
- `msvcrt!free` at `0x18000d282`
- `KERNEL32!DeleteCriticalSection` at `0x18000d26d`
- `KERNEL32!DeleteCriticalSection` at `0x18000d26d`
- `USER32!UnregisterClassA` at `0x18000d23d`
- `USER32!UnregisterClassA` at `0x18000d23d`

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
        JUMPOUT(0x18000D2ADLL);
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
0x18000d1fc  mov     [rsp+arg_0], rbx
0x18000d201  mov     [rsp+arg_8], rsi
0x18000d206  push    rdi
0x18000d207  sub     rsp, 20h
0x18000d20b  mov     rbx, rcx
0x18000d20e  test    rcx, rcx
0x18000d211  jz      short loc_18000D279
0x18000d213  cmp     dword ptr [rcx], 48h ; 'H'
0x18000d216  jnz     short loc_18000D279
0x18000d218  mov     rsi, cs:hInstance
0x18000d21f  xor     edi, edi
0x18000d221  cmp     [rcx+40h], edi
0x18000d224  jle     short loc_18000D24A
0x18000d226  test    edi, edi
0x18000d228  js      short loc_18000D2A8
0x18000d22a  cmp     edi, [rbx+40h]
0x18000d22d  jge     short loc_18000D2A8
0x18000d22f  mov     rax, [rbx+38h]
0x18000d233  mov     rdx, rsi; hInstance
0x18000d236  movsxd  rcx, edi
0x18000d239  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000d23d  call    cs:__imp_UnregisterClassA
0x18000d243  inc     edi
0x18000d245  cmp     edi, [rbx+40h]
0x18000d248  jl      short loc_18000D226
0x18000d24a  mov     rcx, [rbx+38h]; Block
0x18000d24e  test    rcx, rcx
0x18000d251  jz      short loc_18000D261
0x18000d253  call    cs:__imp_free
0x18000d259  mov     qword ptr [rbx+38h], 0
0x18000d261  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d265  mov     qword ptr [rbx+40h], 0
0x18000d26d  call    cs:__imp_DeleteCriticalSection
0x18000d273  mov     dword ptr [rbx], 0
0x18000d279  mov     rcx, [rbx+38h]; Block
0x18000d27d  test    rcx, rcx
0x18000d280  jz      short loc_18000D290
0x18000d282  call    cs:__imp_free
0x18000d288  mov     qword ptr [rbx+38h], 0
0x18000d290  mov     rsi, [rsp+28h+arg_8]
0x18000d295  mov     qword ptr [rbx+40h], 0
0x18000d29d  mov     rbx, [rsp+28h+arg_0]
0x18000d2a2  add     rsp, 20h
0x18000d2a6  pop     rdi
0x18000d2a7  retn
0x18000d2a8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
