# ATL::CAtlWinModule::Term(void)

- ea: `0x180001770`
- end: `0x180001818`
- name: `?Term@CAtlWinModule@ATL@@QEAAXXZ`
- size: `168`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b160`

## callees

- `0x180001770`
- `0x180001b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800017f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800017f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800017e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800017e0`
- `USER32!UnregisterClassA` at `0x1800017c1`
- `USER32!UnregisterClassA` at `0x1800017c1`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::Term(ATL::CAtlWinModule *this)
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
}

```

## disassembly

```asm
0x180001770  test    rcx, rcx
0x180001773  jz      locret_180001817
0x180001779  push    rbx
0x18000177a  sub     rsp, 20h
0x18000177e  cmp     dword ptr [rcx], 48h ; 'H'
0x180001781  mov     rbx, rcx
0x180001784  jnz     loc_180001812
0x18000178a  mov     [rsp+28h+arg_0], rbp
0x18000178f  mov     rbp, cs:hInstance
0x180001796  mov     [rsp+28h+arg_8], rsi
0x18000179b  xor     esi, esi
0x18000179d  mov     [rsp+28h+arg_10], rdi
0x1800017a2  cmp     [rcx+40h], esi
0x1800017a5  jle     short loc_1800017E7
0x1800017a7  test    esi, esi
0x1800017a9  js      short loc_1800017D0
0x1800017ab  cmp     esi, [rbx+40h]
0x1800017ae  lea     rdi, [rbx+38h]
0x1800017b2  jge     short loc_1800017D0
0x1800017b4  mov     rax, [rdi]
0x1800017b7  mov     rdx, rbp; hInstance
0x1800017ba  movsxd  rcx, esi
0x1800017bd  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800017c1  call    cs:__imp_UnregisterClassA
0x1800017c7  inc     esi
0x1800017c9  cmp     esi, [rbx+40h]
0x1800017cc  jl      short loc_1800017A7
0x1800017ce  jmp     short loc_1800017EB
0x1800017d0  xor     r9d, r9d; lpArguments
0x1800017d3  xor     r8d, r8d; nNumberOfArguments
0x1800017d6  mov     edx, 1; dwExceptionFlags
0x1800017db  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800017e0  call    cs:__imp_RaiseException
0x1800017e6  int     3; Trap to Debugger
0x1800017e7  lea     rdi, [rcx+38h]
0x1800017eb  mov     rcx, rdi
0x1800017ee  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800017f3  lea     rcx, [rbx+8]; lpCriticalSection
0x1800017f7  call    cs:__imp_DeleteCriticalSection
0x1800017fd  mov     rdi, [rsp+28h+arg_10]
0x180001802  mov     rbp, [rsp+28h+arg_0]
0x180001807  mov     rsi, [rsp+28h+arg_8]
0x18000180c  mov     dword ptr [rbx], 0
0x180001812  add     rsp, 20h
0x180001816  pop     rbx
0x180001817  retn
```
