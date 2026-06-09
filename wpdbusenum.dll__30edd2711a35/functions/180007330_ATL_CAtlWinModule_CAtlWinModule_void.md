# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180007330`
- end: `0x1800073c0`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015920`

## callees

- `0x180007330`
- `0x1800073c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800073a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800073a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000738c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000738c`
- `USER32!UnregisterClassA` at `0x18000736e`
- `USER32!UnregisterClassA` at `0x18000736e`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  HINSTANCE v2; // rbp
  int v3; // esi
  _QWORD *v4; // rdi

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = hInstance;
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
0x180007330  push    rbx
0x180007332  push    rbp
0x180007333  push    rsi
0x180007334  push    rdi
0x180007335  sub     rsp, 28h
0x180007339  mov     rbx, rcx
0x18000733c  test    rcx, rcx
0x18000733f  jz      short loc_1800073AF
0x180007341  cmp     dword ptr [rcx], 48h ; 'H'
0x180007344  jnz     short loc_1800073AF
0x180007346  mov     rbp, cs:hInstance
0x18000734d  xor     esi, esi
0x18000734f  cmp     [rcx+40h], esi
0x180007352  jle     short loc_180007393
0x180007354  test    esi, esi
0x180007356  js      short loc_18000737D
0x180007358  lea     rdi, [rbx+38h]
0x18000735c  cmp     esi, [rdi+8]
0x18000735f  jge     short loc_18000737D
0x180007361  mov     rax, [rdi]
0x180007364  mov     rdx, rbp; hInstance
0x180007367  movsxd  rcx, esi
0x18000736a  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000736e  call    cs:__imp_UnregisterClassA
0x180007374  inc     esi
0x180007376  cmp     esi, [rbx+40h]
0x180007379  jl      short loc_180007354
0x18000737b  jmp     short loc_180007397
0x18000737d  xor     r9d, r9d; lpArguments
0x180007380  xor     r8d, r8d; nNumberOfArguments
0x180007383  mov     ecx, 0C000008Ch; dwExceptionCode
0x180007388  lea     edx, [r9+1]; dwExceptionFlags
0x18000738c  call    cs:__imp_RaiseException
0x180007392  int     3; Trap to Debugger
0x180007393  lea     rdi, [rcx+38h]
0x180007397  mov     rcx, rdi
0x18000739a  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000739f  lea     rcx, [rbx+8]; lpCriticalSection
0x1800073a3  call    cs:__imp_DeleteCriticalSection
0x1800073a9  mov     dword ptr [rbx], 0
0x1800073af  lea     rcx, [rbx+38h]
0x1800073b3  add     rsp, 28h
0x1800073b7  pop     rdi
0x1800073b8  pop     rsi
0x1800073b9  pop     rbp
0x1800073ba  pop     rbx
0x1800073bb  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
