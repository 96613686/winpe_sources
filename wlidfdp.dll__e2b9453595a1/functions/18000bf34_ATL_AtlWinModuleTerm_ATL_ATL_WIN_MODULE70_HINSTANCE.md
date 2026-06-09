# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000bf34`
- end: `0x18000bfc8`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be9c`

## callees

- `0x18000bf34`
- `0x18000c04c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bfac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bfac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bf95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bf95`
- `USER32!UnregisterClassA` at `0x18000bf77`
- `USER32!UnregisterClassA` at `0x18000bf77`

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
0x18000bf34  push    rbx
0x18000bf36  push    rbp
0x18000bf37  push    rsi
0x18000bf38  push    rdi
0x18000bf39  sub     rsp, 28h
0x18000bf3d  mov     rbp, rdx
0x18000bf40  mov     rbx, rcx
0x18000bf43  test    rcx, rcx
0x18000bf46  jz      short loc_18000BFBA
0x18000bf48  cmp     dword ptr [rcx], 0
0x18000bf4b  jnz     short loc_18000BF51
0x18000bf4d  xor     eax, eax
0x18000bf4f  jmp     short loc_18000BFBF
0x18000bf51  cmp     dword ptr [rcx], 48h ; 'H'
0x18000bf54  jnz     short loc_18000BFBA
0x18000bf56  xor     esi, esi
0x18000bf58  cmp     [rcx+40h], esi
0x18000bf5b  jle     short loc_18000BF9C
0x18000bf5d  test    esi, esi
0x18000bf5f  js      short loc_18000BF86
0x18000bf61  lea     rdi, [rbx+38h]
0x18000bf65  cmp     esi, [rdi+8]
0x18000bf68  jge     short loc_18000BF86
0x18000bf6a  mov     rax, [rdi]
0x18000bf6d  mov     rdx, rbp; hInstance
0x18000bf70  movsxd  rcx, esi
0x18000bf73  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000bf77  call    cs:__imp_UnregisterClassA
0x18000bf7d  inc     esi
0x18000bf7f  cmp     esi, [rbx+40h]
0x18000bf82  jl      short loc_18000BF5D
0x18000bf84  jmp     short loc_18000BFA0
0x18000bf86  xor     r9d, r9d; lpArguments
0x18000bf89  xor     r8d, r8d; nNumberOfArguments
0x18000bf8c  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000bf91  lea     edx, [r9+1]; dwExceptionFlags
0x18000bf95  call    cs:__imp_RaiseException
0x18000bf9b  int     3; Trap to Debugger
0x18000bf9c  lea     rdi, [rcx+38h]
0x18000bfa0  mov     rcx, rdi
0x18000bfa3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000bfa8  lea     rcx, [rbx+8]; lpCriticalSection
0x18000bfac  call    cs:__imp_DeleteCriticalSection
0x18000bfb2  mov     dword ptr [rbx], 0
0x18000bfb8  jmp     short loc_18000BF4D
0x18000bfba  mov     eax, 80070057h
0x18000bfbf  add     rsp, 28h
0x18000bfc3  pop     rdi
0x18000bfc4  pop     rsi
0x18000bfc5  pop     rbp
0x18000bfc6  pop     rbx
0x18000bfc7  retn
```
