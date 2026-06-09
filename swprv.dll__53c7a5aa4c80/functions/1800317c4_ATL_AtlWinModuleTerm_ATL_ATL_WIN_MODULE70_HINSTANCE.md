# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800317c4`
- end: `0x180031858`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180031764`

## callees

- `0x1800317c4`
- `0x180031860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031825`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031825`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003183c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003183c`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180031807`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180031807`

## pseudocode

```c
__int64 __fastcall ATL::AtlWinModuleTerm(struct ATL::_ATL_WIN_MODULE70 *a1, HINSTANCE a2)
{
  int v5; // esi
  _QWORD *v6; // rdi

  if ( a1 )
  {
    if ( !*(_DWORD *)a1 )
      return 0;
    if ( *(_DWORD *)a1 == 72 )
    {
      v5 = 0;
      if ( *((int *)a1 + 16) <= 0 )
      {
        v6 = (_QWORD *)((char *)a1 + 56);
      }
      else
      {
        do
        {
          if ( v5 < 0 || (v6 = (_QWORD *)((char *)a1 + 56), v5 >= *((_DWORD *)a1 + 16)) )
          {
            RaiseException(0xC000008C, 1u, 0, 0);
            __debugbreak();
          }
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
        }
        while ( v5 < *((_DWORD *)a1 + 16) );
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v6);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
      *(_DWORD *)a1 = 0;
      return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800317c4  push    rbx
0x1800317c6  push    rbp
0x1800317c7  push    rsi
0x1800317c8  push    rdi
0x1800317c9  sub     rsp, 28h
0x1800317cd  mov     rbp, rdx
0x1800317d0  mov     rbx, rcx
0x1800317d3  test    rcx, rcx
0x1800317d6  jz      short loc_18003184A
0x1800317d8  cmp     dword ptr [rcx], 0
0x1800317db  jnz     short loc_1800317E1
0x1800317dd  xor     eax, eax
0x1800317df  jmp     short loc_18003184F
0x1800317e1  cmp     dword ptr [rcx], 48h ; 'H'
0x1800317e4  jnz     short loc_18003184A
0x1800317e6  xor     esi, esi
0x1800317e8  cmp     [rcx+40h], esi
0x1800317eb  jle     short loc_18003182C
0x1800317ed  test    esi, esi
0x1800317ef  js      short loc_180031816
0x1800317f1  lea     rdi, [rbx+38h]
0x1800317f5  cmp     esi, [rdi+8]
0x1800317f8  jge     short loc_180031816
0x1800317fa  mov     rax, [rdi]
0x1800317fd  mov     rdx, rbp; hInstance
0x180031800  movsxd  rcx, esi
0x180031803  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180031807  call    cs:__imp_UnregisterClassA
0x18003180d  inc     esi
0x18003180f  cmp     esi, [rbx+40h]
0x180031812  jl      short loc_1800317ED
0x180031814  jmp     short loc_180031830
0x180031816  xor     r9d, r9d; lpArguments
0x180031819  xor     r8d, r8d; nNumberOfArguments
0x18003181c  mov     ecx, 0C000008Ch; dwExceptionCode
0x180031821  lea     edx, [r9+1]; dwExceptionFlags
0x180031825  call    cs:__imp_RaiseException
0x18003182b  int     3; Trap to Debugger
0x18003182c  lea     rdi, [rcx+38h]
0x180031830  mov     rcx, rdi
0x180031833  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180031838  lea     rcx, [rbx+8]; lpCriticalSection
0x18003183c  call    cs:__imp_DeleteCriticalSection
0x180031842  mov     dword ptr [rbx], 0
0x180031848  jmp     short loc_1800317DD
0x18003184a  mov     eax, 80070057h
0x18003184f  add     rsp, 28h
0x180031853  pop     rdi
0x180031854  pop     rsi
0x180031855  pop     rbp
0x180031856  pop     rbx
0x180031857  retn
```
