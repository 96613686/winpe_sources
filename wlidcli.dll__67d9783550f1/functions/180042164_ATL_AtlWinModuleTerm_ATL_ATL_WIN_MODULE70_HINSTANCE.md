# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180042164`
- end: `0x1800421f8`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800420cc`

## callees

- `0x180042164`
- `0x18004227c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800421dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800421dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800421c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800421c5`
- `USER32!UnregisterClassA` at `0x1800421a7`
- `USER32!UnregisterClassA` at `0x1800421a7`

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
0x180042164  push    rbx
0x180042166  push    rbp
0x180042167  push    rsi
0x180042168  push    rdi
0x180042169  sub     rsp, 28h
0x18004216d  mov     rbp, rdx
0x180042170  mov     rbx, rcx
0x180042173  test    rcx, rcx
0x180042176  jz      short loc_1800421EA
0x180042178  cmp     dword ptr [rcx], 0
0x18004217b  jnz     short loc_180042181
0x18004217d  xor     eax, eax
0x18004217f  jmp     short loc_1800421EF
0x180042181  cmp     dword ptr [rcx], 48h ; 'H'
0x180042184  jnz     short loc_1800421EA
0x180042186  xor     esi, esi
0x180042188  cmp     [rcx+40h], esi
0x18004218b  jle     short loc_1800421CC
0x18004218d  test    esi, esi
0x18004218f  js      short loc_1800421B6
0x180042191  lea     rdi, [rbx+38h]
0x180042195  cmp     esi, [rdi+8]
0x180042198  jge     short loc_1800421B6
0x18004219a  mov     rax, [rdi]
0x18004219d  mov     rdx, rbp; hInstance
0x1800421a0  movsxd  rcx, esi
0x1800421a3  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800421a7  call    cs:__imp_UnregisterClassA
0x1800421ad  inc     esi
0x1800421af  cmp     esi, [rbx+40h]
0x1800421b2  jl      short loc_18004218D
0x1800421b4  jmp     short loc_1800421D0
0x1800421b6  xor     r9d, r9d; lpArguments
0x1800421b9  xor     r8d, r8d; nNumberOfArguments
0x1800421bc  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800421c1  lea     edx, [r9+1]; dwExceptionFlags
0x1800421c5  call    cs:__imp_RaiseException
0x1800421cb  int     3; Trap to Debugger
0x1800421cc  lea     rdi, [rcx+38h]
0x1800421d0  mov     rcx, rdi
0x1800421d3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800421d8  lea     rcx, [rbx+8]; lpCriticalSection
0x1800421dc  call    cs:__imp_DeleteCriticalSection
0x1800421e2  mov     dword ptr [rbx], 0
0x1800421e8  jmp     short loc_18004217D
0x1800421ea  mov     eax, 80070057h
0x1800421ef  add     rsp, 28h
0x1800421f3  pop     rdi
0x1800421f4  pop     rsi
0x1800421f5  pop     rbp
0x1800421f6  pop     rbx
0x1800421f7  retn
```
