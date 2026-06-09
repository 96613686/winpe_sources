# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000f598`
- end: `0x18000f628`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030b20`

## callees

- `0x18000f598`
- `0x18000f630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f60b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f60b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f5f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f5f4`
- `USER32!UnregisterClassA` at `0x18000f5d6`
- `USER32!UnregisterClassA` at `0x18000f5d6`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  HINSTANCE v2; // rbp
  int v3; // esi
  _QWORD *v4; // rdi

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = hModule;
    v3 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v4 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v3 < 0 || (v4 = (_QWORD *)((char *)this + 56), v3 >= *((_DWORD *)this + 16)) )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          __debugbreak();
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v4 + 2LL * v3++), v2);
      }
      while ( v3 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x18000f598  push    rbx
0x18000f59a  push    rbp
0x18000f59b  push    rsi
0x18000f59c  push    rdi
0x18000f59d  sub     rsp, 28h
0x18000f5a1  mov     rbx, rcx
0x18000f5a4  test    rcx, rcx
0x18000f5a7  jz      short loc_18000F617
0x18000f5a9  cmp     dword ptr [rcx], 48h ; 'H'
0x18000f5ac  jnz     short loc_18000F617
0x18000f5ae  mov     rbp, cs:hModule
0x18000f5b5  xor     esi, esi
0x18000f5b7  cmp     [rcx+40h], esi
0x18000f5ba  jle     short loc_18000F5FB
0x18000f5bc  test    esi, esi
0x18000f5be  js      short loc_18000F5E5
0x18000f5c0  lea     rdi, [rbx+38h]
0x18000f5c4  cmp     esi, [rdi+8]
0x18000f5c7  jge     short loc_18000F5E5
0x18000f5c9  mov     rax, [rdi]
0x18000f5cc  mov     rdx, rbp; hInstance
0x18000f5cf  movsxd  rcx, esi
0x18000f5d2  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000f5d6  call    cs:__imp_UnregisterClassA
0x18000f5dc  inc     esi
0x18000f5de  cmp     esi, [rbx+40h]
0x18000f5e1  jl      short loc_18000F5BC
0x18000f5e3  jmp     short loc_18000F5FF
0x18000f5e5  xor     r9d, r9d; lpArguments
0x18000f5e8  xor     r8d, r8d; nNumberOfArguments
0x18000f5eb  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000f5f0  lea     edx, [r9+1]; dwExceptionFlags
0x18000f5f4  call    cs:__imp_RaiseException
0x18000f5fa  int     3; Trap to Debugger
0x18000f5fb  lea     rdi, [rcx+38h]
0x18000f5ff  mov     rcx, rdi
0x18000f602  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000f607  lea     rcx, [rbx+8]; lpCriticalSection
0x18000f60b  call    cs:__imp_DeleteCriticalSection
0x18000f611  mov     dword ptr [rbx], 0
0x18000f617  lea     rcx, [rbx+38h]
0x18000f61b  add     rsp, 28h
0x18000f61f  pop     rdi
0x18000f620  pop     rsi
0x18000f621  pop     rbp
0x18000f622  pop     rbx
0x18000f623  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
