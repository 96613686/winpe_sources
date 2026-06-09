# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000e3a4`
- end: `0x18000e438`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e30c`

## callees

- `0x18000e3a4`
- `0x18000e4bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e405`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e405`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e41c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e41c`
- `USER32!UnregisterClassA` at `0x18000e3e7`
- `USER32!UnregisterClassA` at `0x18000e3e7`

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
0x18000e3a4  push    rbx
0x18000e3a6  push    rbp
0x18000e3a7  push    rsi
0x18000e3a8  push    rdi
0x18000e3a9  sub     rsp, 28h
0x18000e3ad  mov     rbp, rdx
0x18000e3b0  mov     rbx, rcx
0x18000e3b3  test    rcx, rcx
0x18000e3b6  jz      short loc_18000E42A
0x18000e3b8  cmp     dword ptr [rcx], 0
0x18000e3bb  jnz     short loc_18000E3C1
0x18000e3bd  xor     eax, eax
0x18000e3bf  jmp     short loc_18000E42F
0x18000e3c1  cmp     dword ptr [rcx], 48h ; 'H'
0x18000e3c4  jnz     short loc_18000E42A
0x18000e3c6  xor     esi, esi
0x18000e3c8  cmp     [rcx+40h], esi
0x18000e3cb  jle     short loc_18000E40C
0x18000e3cd  test    esi, esi
0x18000e3cf  js      short loc_18000E3F6
0x18000e3d1  lea     rdi, [rbx+38h]
0x18000e3d5  cmp     esi, [rdi+8]
0x18000e3d8  jge     short loc_18000E3F6
0x18000e3da  mov     rax, [rdi]
0x18000e3dd  mov     rdx, rbp; hInstance
0x18000e3e0  movsxd  rcx, esi
0x18000e3e3  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000e3e7  call    cs:__imp_UnregisterClassA
0x18000e3ed  inc     esi
0x18000e3ef  cmp     esi, [rbx+40h]
0x18000e3f2  jl      short loc_18000E3CD
0x18000e3f4  jmp     short loc_18000E410
0x18000e3f6  xor     r9d, r9d; lpArguments
0x18000e3f9  xor     r8d, r8d; nNumberOfArguments
0x18000e3fc  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000e401  lea     edx, [r9+1]; dwExceptionFlags
0x18000e405  call    cs:__imp_RaiseException
0x18000e40b  int     3; Trap to Debugger
0x18000e40c  lea     rdi, [rcx+38h]
0x18000e410  mov     rcx, rdi
0x18000e413  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000e418  lea     rcx, [rbx+8]; lpCriticalSection
0x18000e41c  call    cs:__imp_DeleteCriticalSection
0x18000e422  mov     dword ptr [rbx], 0
0x18000e428  jmp     short loc_18000E3BD
0x18000e42a  mov     eax, 80070057h
0x18000e42f  add     rsp, 28h
0x18000e433  pop     rdi
0x18000e434  pop     rsi
0x18000e435  pop     rbp
0x18000e436  pop     rbx
0x18000e437  retn
```
