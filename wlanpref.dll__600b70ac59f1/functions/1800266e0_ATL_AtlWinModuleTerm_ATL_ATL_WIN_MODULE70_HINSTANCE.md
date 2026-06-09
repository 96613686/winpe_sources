# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800266e0`
- end: `0x180026774`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026680`

## callees

- `0x1800266e0`
- `0x18002677c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026741`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026741`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026758`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026758`
- `USER32!UnregisterClassA` at `0x180026723`
- `USER32!UnregisterClassA` at `0x180026723`

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
0x1800266e0  push    rbx
0x1800266e2  push    rbp
0x1800266e3  push    rsi
0x1800266e4  push    rdi
0x1800266e5  sub     rsp, 28h
0x1800266e9  mov     rbp, rdx
0x1800266ec  mov     rbx, rcx
0x1800266ef  test    rcx, rcx
0x1800266f2  jz      short loc_180026766
0x1800266f4  cmp     dword ptr [rcx], 0
0x1800266f7  jnz     short loc_1800266FD
0x1800266f9  xor     eax, eax
0x1800266fb  jmp     short loc_18002676B
0x1800266fd  cmp     dword ptr [rcx], 48h ; 'H'
0x180026700  jnz     short loc_180026766
0x180026702  xor     esi, esi
0x180026704  cmp     [rcx+40h], esi
0x180026707  jle     short loc_180026748
0x180026709  test    esi, esi
0x18002670b  js      short loc_180026732
0x18002670d  lea     rdi, [rbx+38h]
0x180026711  cmp     esi, [rdi+8]
0x180026714  jge     short loc_180026732
0x180026716  mov     rax, [rdi]
0x180026719  mov     rdx, rbp; hInstance
0x18002671c  movsxd  rcx, esi
0x18002671f  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180026723  call    cs:__imp_UnregisterClassA
0x180026729  inc     esi
0x18002672b  cmp     esi, [rbx+40h]
0x18002672e  jl      short loc_180026709
0x180026730  jmp     short loc_18002674C
0x180026732  xor     r9d, r9d; lpArguments
0x180026735  xor     r8d, r8d; nNumberOfArguments
0x180026738  mov     ecx, 0C000008Ch; dwExceptionCode
0x18002673d  lea     edx, [r9+1]; dwExceptionFlags
0x180026741  call    cs:__imp_RaiseException
0x180026747  int     3; Trap to Debugger
0x180026748  lea     rdi, [rcx+38h]
0x18002674c  mov     rcx, rdi
0x18002674f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180026754  lea     rcx, [rbx+8]; lpCriticalSection
0x180026758  call    cs:__imp_DeleteCriticalSection
0x18002675e  mov     dword ptr [rbx], 0
0x180026764  jmp     short loc_1800266F9
0x180026766  mov     eax, 80070057h
0x18002676b  add     rsp, 28h
0x18002676f  pop     rdi
0x180026770  pop     rsi
0x180026771  pop     rbp
0x180026772  pop     rbx
0x180026773  retn
```
