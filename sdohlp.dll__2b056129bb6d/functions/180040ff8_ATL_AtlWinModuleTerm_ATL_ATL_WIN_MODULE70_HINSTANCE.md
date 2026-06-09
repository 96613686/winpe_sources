# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x180040ff8`
- end: `0x18004108c`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180040f98`

## callees

- `0x180040ff8`
- `0x180041094`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180041070`
- `KERNEL32!DeleteCriticalSection` at `0x180041070`
- `KERNEL32!RaiseException` at `0x180041059`
- `KERNEL32!RaiseException` at `0x180041059`
- `USER32!UnregisterClassA` at `0x18004103b`
- `USER32!UnregisterClassA` at `0x18004103b`

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
0x180040ff8  push    rbx
0x180040ffa  push    rbp
0x180040ffb  push    rsi
0x180040ffc  push    rdi
0x180040ffd  sub     rsp, 28h
0x180041001  mov     rbp, rdx
0x180041004  mov     rbx, rcx
0x180041007  test    rcx, rcx
0x18004100a  jz      short loc_18004107E
0x18004100c  cmp     dword ptr [rcx], 0
0x18004100f  jnz     short loc_180041015
0x180041011  xor     eax, eax
0x180041013  jmp     short loc_180041083
0x180041015  cmp     dword ptr [rcx], 48h ; 'H'
0x180041018  jnz     short loc_18004107E
0x18004101a  xor     esi, esi
0x18004101c  cmp     [rcx+40h], esi
0x18004101f  jle     short loc_180041060
0x180041021  test    esi, esi
0x180041023  js      short loc_18004104A
0x180041025  lea     rdi, [rbx+38h]
0x180041029  cmp     esi, [rdi+8]
0x18004102c  jge     short loc_18004104A
0x18004102e  mov     rax, [rdi]
0x180041031  mov     rdx, rbp; hInstance
0x180041034  movsxd  rcx, esi
0x180041037  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18004103b  call    cs:__imp_UnregisterClassA
0x180041041  inc     esi
0x180041043  cmp     esi, [rbx+40h]
0x180041046  jl      short loc_180041021
0x180041048  jmp     short loc_180041064
0x18004104a  xor     r9d, r9d; lpArguments
0x18004104d  xor     r8d, r8d; nNumberOfArguments
0x180041050  mov     ecx, 0C000008Ch; dwExceptionCode
0x180041055  lea     edx, [r9+1]; dwExceptionFlags
0x180041059  call    cs:__imp_RaiseException
0x18004105f  int     3; Trap to Debugger
0x180041060  lea     rdi, [rcx+38h]
0x180041064  mov     rcx, rdi
0x180041067  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18004106c  lea     rcx, [rbx+8]; lpCriticalSection
0x180041070  call    cs:__imp_DeleteCriticalSection
0x180041076  mov     dword ptr [rbx], 0
0x18004107c  jmp     short loc_180041011
0x18004107e  mov     eax, 80070057h
0x180041083  add     rsp, 28h
0x180041087  pop     rdi
0x180041088  pop     rsi
0x180041089  pop     rbp
0x18004108a  pop     rbx
0x18004108b  retn
```
