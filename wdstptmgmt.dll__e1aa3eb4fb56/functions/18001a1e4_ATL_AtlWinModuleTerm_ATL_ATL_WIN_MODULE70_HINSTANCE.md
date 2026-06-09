# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18001a1e4`
- end: `0x18001a295`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `177`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a180`

## callees

- `0x180005c28`
- `0x18001a1e4`
- `0x18001a29c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a258`
- `KERNEL32!DeleteCriticalSection` at `0x18001a258`
- `USER32!UnregisterClassA` at `0x18001a234`
- `USER32!UnregisterClassA` at `0x18001a234`

## pseudocode

```c
__int64 __fastcall ATL::AtlWinModuleTerm(struct ATL::_ATL_WIN_MODULE70 *a1, HINSTANCE a2)
{
  int v5; // ebp
  __int64 v6; // rsi

  if ( a1 )
  {
    if ( !*(_DWORD *)a1 )
      return 0;
    if ( *(_DWORD *)a1 == 72 )
    {
      v5 = 0;
      if ( *((int *)a1 + 16) > 0 )
      {
        v6 = 0;
        do
        {
          if ( v6 < 0 || v5 >= *((_DWORD *)a1 + 16) )
          {
            ATL::_AtlRaiseException(0xC000008C, (unsigned int)a2);
            __debugbreak();
          }
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)a1 + 7) + v6), a2);
          ++v5;
          v6 += 2;
        }
        while ( v5 < *((_DWORD *)a1 + 16) );
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)a1 + 56);
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
0x18001a1e4  mov     rax, rsp
0x18001a1e7  mov     [rax+8], rbx
0x18001a1eb  mov     [rax+10h], rbp
0x18001a1ef  mov     [rax+18h], rsi
0x18001a1f3  mov     [rax+20h], rdi
0x18001a1f7  push    r14
0x18001a1f9  sub     rsp, 20h
0x18001a1fd  mov     r14, rdx
0x18001a200  mov     rbx, rcx
0x18001a203  test    rcx, rcx
0x18001a206  jz      short loc_18001A274
0x18001a208  cmp     dword ptr [rcx], 0
0x18001a20b  jnz     short loc_18001A211
0x18001a20d  xor     eax, eax
0x18001a20f  jmp     short loc_18001A279
0x18001a211  cmp     dword ptr [rcx], 48h ; 'H'
0x18001a214  jnz     short loc_18001A274
0x18001a216  xor     ebp, ebp
0x18001a218  cmp     [rcx+40h], ebp
0x18001a21b  jle     short loc_18001A24B
0x18001a21d  xor     esi, esi
0x18001a21f  test    rsi, rsi
0x18001a222  js      short loc_18001A269
0x18001a224  cmp     ebp, [rbx+40h]
0x18001a227  jge     short loc_18001A269
0x18001a229  mov     rax, [rbx+38h]
0x18001a22d  mov     rdx, r14; hInstance
0x18001a230  movzx   ecx, word ptr [rax+rsi]; lpClassName
0x18001a234  call    cs:__imp_UnregisterClassA
0x18001a23b  nop     dword ptr [rax+rax+00h]
0x18001a240  inc     ebp
0x18001a242  add     rsi, 2
0x18001a246  cmp     ebp, [rbx+40h]
0x18001a249  jl      short loc_18001A21F
0x18001a24b  lea     rcx, [rbx+38h]
0x18001a24f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18001a254  lea     rcx, [rbx+8]; lpCriticalSection
0x18001a258  call    cs:__imp_DeleteCriticalSection
0x18001a25f  nop     dword ptr [rax+rax+00h]
0x18001a264  and     dword ptr [rbx], 0
0x18001a267  jmp     short loc_18001A20D
0x18001a269  mov     ecx, 0C000008Ch; unsigned int
0x18001a26e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18001a273  int     3; Trap to Debugger
0x18001a274  mov     eax, 80070057h
0x18001a279  mov     rbx, [rsp+28h+arg_0]
0x18001a27e  mov     rbp, [rsp+28h+arg_8]
0x18001a283  mov     rsi, [rsp+28h+arg_10]
0x18001a288  mov     rdi, [rsp+28h+arg_18]
0x18001a28d  add     rsp, 20h
0x18001a291  pop     r14
0x18001a293  retn
```
