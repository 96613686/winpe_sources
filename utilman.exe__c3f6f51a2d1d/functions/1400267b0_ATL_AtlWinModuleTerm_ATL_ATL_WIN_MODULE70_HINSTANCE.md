# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1400267b0`
- end: `0x140026861`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `177`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140026710`

## callees

- `0x1400267b0`
- `0x140026940`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002683b`
- `KERNEL32!DeleteCriticalSection` at `0x14002683b`
- `KERNEL32!RaiseException` at `0x14002681e`
- `KERNEL32!RaiseException` at `0x14002681e`
- `USER32!UnregisterClassA` at `0x1400267fa`
- `USER32!UnregisterClassA` at `0x1400267fa`

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
      if ( *((int *)a1 + 16) > 0 )
      {
        while ( v5 >= 0 )
        {
          v6 = (_QWORD *)((char *)a1 + 56);
          if ( v5 >= *((_DWORD *)a1 + 16) )
            break;
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
          if ( v5 >= *((_DWORD *)a1 + 16) )
            goto LABEL_12;
        }
        RaiseException(0xC000008C, 1u, 0, 0);
        __debugbreak();
      }
      v6 = (_QWORD *)((char *)a1 + 56);
LABEL_12:
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
0x1400267b0  push    rbx
0x1400267b2  push    rbp
0x1400267b3  push    rsi
0x1400267b4  push    rdi
0x1400267b5  sub     rsp, 28h
0x1400267b9  mov     rbp, rdx
0x1400267bc  mov     rbx, rcx
0x1400267bf  test    rcx, rcx
0x1400267c2  jz      loc_140026852
0x1400267c8  cmp     dword ptr [rcx], 0
0x1400267cb  jnz     short loc_1400267D4
0x1400267cd  xor     eax, eax
0x1400267cf  jmp     loc_140026857
0x1400267d4  cmp     dword ptr [rcx], 48h ; 'H'
0x1400267d7  jnz     short loc_140026852
0x1400267d9  xor     esi, esi
0x1400267db  cmp     [rcx+40h], esi
0x1400267de  jle     short loc_14002682B
0x1400267e0  test    esi, esi
0x1400267e2  js      short loc_14002680F
0x1400267e4  lea     rdi, [rbx+38h]
0x1400267e8  cmp     esi, [rdi+8]
0x1400267eb  jge     short loc_14002680F
0x1400267ed  mov     rax, [rdi]
0x1400267f0  mov     rdx, rbp; hInstance
0x1400267f3  movsxd  rcx, esi
0x1400267f6  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1400267fa  call    cs:__imp_UnregisterClassA
0x140026801  nop     dword ptr [rax+rax+00h]
0x140026806  inc     esi
0x140026808  cmp     esi, [rbx+40h]
0x14002680b  jl      short loc_1400267E0
0x14002680d  jmp     short loc_14002682F
0x14002680f  xor     r9d, r9d; lpArguments
0x140026812  xor     r8d, r8d; nNumberOfArguments
0x140026815  mov     ecx, 0C000008Ch; dwExceptionCode
0x14002681a  lea     edx, [r9+1]; dwExceptionFlags
0x14002681e  call    cs:__imp_RaiseException
0x140026825  nop     dword ptr [rax+rax+00h]
0x14002682a  int     3; Trap to Debugger
0x14002682b  lea     rdi, [rcx+38h]
0x14002682f  mov     rcx, rdi
0x140026832  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x140026837  lea     rcx, [rbx+8]; lpCriticalSection
0x14002683b  call    cs:__imp_DeleteCriticalSection
0x140026842  nop     dword ptr [rax+rax+00h]
0x140026847  mov     dword ptr [rbx], 0
0x14002684d  jmp     loc_1400267CD
0x140026852  mov     eax, 80070057h
0x140026857  add     rsp, 28h
0x14002685b  pop     rdi
0x14002685c  pop     rsi
0x14002685d  pop     rbp
0x14002685e  pop     rbx
0x14002685f  retn
```
