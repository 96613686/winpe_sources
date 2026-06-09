# ValidateHandle

- ea: `0x180007560`
- end: `0x180007631`
- name: `ValidateHandle`
- size: `209`
- prototype: ``
- caller_count: `85`
- callee_count: `2`
- tags: ``

## callers

- `0x180006300`
- `0x180006ba0`
- `0x180007020`
- `0x180007420`
- `0x180007640`
- `0x1800076b0`
- `0x1800077ec`
- `0x1800078f4`
- `0x180007b00`
- `0x180008530`
- `0x1800085a0`
- `0x180009160`
- `0x180009250`
- `0x180009300`
- `0x1800093a0`
- `0x1800096f0`
- `0x180009760`
- `0x180009820`
- `0x180009de0`
- `0x18000a790`
- `0x18000b364`
- `0x18000b744`
- `0x18000bee0`
- `0x18000c1d0`
- `0x18000c6a0`
- `0x18000e000`
- `0x18000e720`
- `0x18000e860`
- `0x18000ec90`
- `0x18000ed70`
- `0x18000eff0`
- `0x18000f280`
- `0x18000f950`
- `0x18000fa80`
- `0x180010130`
- `0x180011e60`
- `0x180012640`
- `0x180012690`
- `0x18001787c`
- `0x180017b20`
- `0x1800183c0`
- `0x180018680`
- `0x1800186c0`
- `0x180018730`
- `0x1800187a0`
- `0x180018930`
- `0x180018a10`
- `0x180018ae0`
- `0x180018bb0`
- `0x180018df0`

## callees

- `0x180007560`
- `0x180012d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007601`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007601`

## pseudocode

```c
_BOOL8 __fastcall ValidateHandle(unsigned __int64 a1, int a2)
{
  unsigned __int64 v4; // rbx
  _QWORD *i; // rax

  if ( a1 < 0x10000 || a1 == -1 || a1 > gdwMaxVirtualAddress || a1 == 0xFFFFFFFF || a1 < gdwMinVirtualAddress )
    return 0;
  v4 = a1 - 80;
  EnterCriticalSection(&HandleListCritSec);
  for ( i = (_QWORD *)pHandleList; i; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)v4 )
    {
      LeaveCriticalSection(&HandleListCritSec);
      return *(_DWORD *)(v4 + 8) == a2;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
  }
  LeaveCriticalSection(&HandleListCritSec);
  return 0;
}

```

## disassembly

```asm
0x180007560  push    rdi
0x180007562  sub     rsp, 20h
0x180007566  mov     edi, edx
0x180007568  cmp     rcx, 10000h
0x18000756f  jb      short loc_180007585
0x180007571  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007575  jz      short loc_180007585
0x180007577  cmp     rcx, cs:gdwMaxVirtualAddress
0x18000757e  mov     eax, 0FFFFFFFFh
0x180007583  jbe     short loc_18000758D
0x180007585  xor     eax, eax
0x180007587  add     rsp, 20h
0x18000758b  pop     rdi
0x18000758c  retn
0x18000758d  cmp     rcx, rax
0x180007590  jz      short loc_180007585
0x180007592  cmp     rcx, cs:gdwMinVirtualAddress
0x180007599  jb      short loc_180007585
0x18000759b  mov     [rsp+28h+arg_0], rbx
0x1800075a0  lea     rbx, [rcx-50h]
0x1800075a4  lea     rcx, HandleListCritSec; lpCriticalSection
0x1800075ab  call    cs:__imp_EnterCriticalSection
0x1800075b1  mov     rax, cs:pHandleList
0x1800075b8  test    rax, rax
0x1800075bb  jz      short loc_1800075E7
0x1800075bd  cmp     rax, rbx
0x1800075c0  jz      short loc_1800075C7
0x1800075c2  mov     rax, [rax]
0x1800075c5  jmp     short loc_1800075B8
0x1800075c7  lea     rcx, HandleListCritSec; lpCriticalSection
0x1800075ce  call    cs:__imp_LeaveCriticalSection
0x1800075d4  xor     eax, eax
0x1800075d6  cmp     [rbx+8], edi
0x1800075d9  setz    al
0x1800075dc  mov     rbx, [rsp+28h+arg_0]
0x1800075e1  add     rsp, 20h
0x1800075e5  pop     rdi
0x1800075e6  retn
0x1800075e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075ee  lea     rax, WPP_GLOBAL_Control
0x1800075f5  cmp     rcx, rax
0x1800075f8  jnz     short loc_18000760B
0x1800075fa  lea     rcx, HandleListCritSec; lpCriticalSection
0x180007601  call    cs:__imp_LeaveCriticalSection
0x180007607  xor     eax, eax
0x180007609  jmp     short loc_1800075DC
0x18000760b  test    dword ptr [rcx+1Ch], 400000h
0x180007612  jz      short loc_1800075FA
0x180007614  cmp     byte ptr [rcx+19h], 1
0x180007618  jb      short loc_1800075FA
0x18000761a  mov     rcx, [rcx+10h]
0x18000761e  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x180007625  mov     edx, 0Ah
0x18000762a  call    WPP_SF_
0x18000762f  jmp     short loc_1800075FA
```
