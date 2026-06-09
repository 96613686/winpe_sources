# CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerComStore *)

- ea: `0x18000e3fc`
- end: `0x18000e494`
- name: `?TryGetWerStoreApiLock@CWerStoreApiAutoLock@@QEAAJPEAVCWerComStore@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(CWerStoreApiAutoLock *__hidden this, struct CWerComStore *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000aa40`
- `0x18000ef80`
- `0x18000f148`
- `0x18000fb0c`
- `0x18000fd54`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e3fc`

## pseudocode

```c
__int64 __fastcall CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerStoreApiAutoLock *this, struct CWerComStore *a2)
{
  unsigned int v3; // ebx

  if ( a2 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)a2 + 10, 1, 0) )
    {
      v3 = -2147024726;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, 2147942570LL);
    }
    else
    {
      *(_QWORD *)this = a2;
      return 0;
    }
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000e3fc  push    rbx
0x18000e3fe  sub     rsp, 20h
0x18000e402  mov     r8, rdx
0x18000e405  test    rdx, rdx
0x18000e408  jnz     short loc_18000E441
0x18000e40a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e411  lea     rax, WPP_GLOBAL_Control
0x18000e418  cmp     rcx, rax
0x18000e41b  jz      short loc_18000E43A
0x18000e41d  lea     edx, [r8+1]
0x18000e421  test    [rcx+1Ch], dl
0x18000e424  jz      short loc_18000E43A
0x18000e426  mov     rcx, [rcx+10h]
0x18000e42a  lea     edx, [r8+17h]
0x18000e42e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e435  call    WPP_SF_
0x18000e43a  mov     eax, 80070057h
0x18000e43f  jmp     short loc_18000E48E
0x18000e441  mov     edx, 1
0x18000e446  xor     eax, eax
0x18000e448  lock cmpxchg [r8+28h], edx
0x18000e44e  jz      short loc_18000E487
0x18000e450  mov     ebx, 800700AAh
0x18000e455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e45c  lea     rax, WPP_GLOBAL_Control
0x18000e463  cmp     rcx, rax
0x18000e466  jz      short loc_18000E48C
0x18000e468  test    [rcx+1Ch], dl
0x18000e46b  jz      short loc_18000E48C
0x18000e46d  mov     rcx, [rcx+10h]
0x18000e471  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e478  mov     edx, 18h
0x18000e47d  mov     r9d, ebx
0x18000e480  call    WPP_SF_d
0x18000e485  jmp     short loc_18000E48C
0x18000e487  mov     [rcx], r8
0x18000e48a  xor     ebx, ebx
0x18000e48c  mov     eax, ebx
0x18000e48e  add     rsp, 20h
0x18000e492  pop     rbx
0x18000e493  retn
```
