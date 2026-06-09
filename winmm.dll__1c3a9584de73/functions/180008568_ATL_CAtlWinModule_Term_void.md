# ATL::CAtlWinModule::Term(void)

- ea: `0x180008568`
- end: `0x1800085ef`
- name: `?Term@CAtlWinModule@ATL@@QEAAXXZ`
- size: `135`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008540`

## callees

- `0x180008568`
- `0x1800085f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000859b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000859b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800085e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800085e8`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x1800085ca`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x1800085ca`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::Term(ATL::CAtlWinModule *this)
{
  HINSTANCE v2; // rbp
  int v3; // esi
  _QWORD *v4; // rdi

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = hModule;
    v3 = 0;
    if ( *((int *)this + 16) > 0 )
    {
      do
      {
        if ( v3 < 0 || (v4 = (_QWORD *)((char *)this + 56), v3 >= *((_DWORD *)this + 16)) )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          JUMPOUT(0x1800085EELL);
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v4 + 2LL * v3++), v2);
      }
      while ( v3 < *((_DWORD *)this + 16) );
    }
    else
    {
      v4 = (_QWORD *)((char *)this + 56);
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180008568  test    rcx, rcx
0x18000856b  jz      short locret_1800085AF
0x18000856d  push    rbx
0x18000856e  push    rbp
0x18000856f  push    rsi
0x180008570  push    rdi
0x180008571  sub     rsp, 28h
0x180008575  cmp     dword ptr [rcx], 48h ; 'H'
0x180008578  mov     rbx, rcx
0x18000857b  jnz     short loc_1800085A7
0x18000857d  mov     rbp, cs:hModule
0x180008584  xor     esi, esi
0x180008586  cmp     [rcx+40h], esi
0x180008589  jg      short loc_1800085B0
0x18000858b  lea     rdi, [rcx+38h]
0x18000858f  mov     rcx, rdi
0x180008592  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180008597  lea     rcx, [rbx+8]; lpCriticalSection
0x18000859b  call    cs:__imp_DeleteCriticalSection
0x1800085a1  mov     dword ptr [rbx], 0
0x1800085a7  add     rsp, 28h
0x1800085ab  pop     rdi
0x1800085ac  pop     rsi
0x1800085ad  pop     rbp
0x1800085ae  pop     rbx
0x1800085af  retn
0x1800085b0  test    esi, esi
0x1800085b2  js      short loc_1800085D9
0x1800085b4  lea     rdi, [rbx+38h]
0x1800085b8  cmp     esi, [rdi+8]
0x1800085bb  jge     short loc_1800085D9
0x1800085bd  mov     rax, [rdi]
0x1800085c0  mov     rdx, rbp; hInstance
0x1800085c3  movsxd  rcx, esi
0x1800085c6  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800085ca  call    cs:__imp_UnregisterClassA
0x1800085d0  inc     esi
0x1800085d2  cmp     esi, [rbx+40h]
0x1800085d5  jl      short loc_1800085B0
0x1800085d7  jmp     short loc_18000858F
0x1800085d9  xor     r9d, r9d; lpArguments
0x1800085dc  xor     r8d, r8d; nNumberOfArguments
0x1800085df  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800085e4  lea     edx, [r9+1]; dwExceptionFlags
0x1800085e8  call    cs:__imp_RaiseException
```
