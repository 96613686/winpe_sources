# CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)

- ea: `0x18000e35c`
- end: `0x18000e3f4`
- name: `?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(CWerApiAutoLock *__hidden this, struct CWerComReport *)`
- caller_count: `20`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f46c`
- `0x18000f59c`
- `0x18000f6c8`
- `0x18000f7f8`
- `0x18000f9dc`
- `0x18000fef4`
- `0x1800101bc`
- `0x180010508`
- `0x180010650`
- `0x180010734`
- `0x1800108f4`
- `0x180010b28`
- `0x180010d10`
- `0x180010f58`
- `0x180011240`
- `0x180011310`
- `0x180011620`
- `0x1800117a0`
- `0x180011860`
- `0x180011aa0`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`

## pseudocode

```c
__int64 __fastcall CWerApiAutoLock::TryGetWerApiLock(CWerApiAutoLock *this, struct CWerComReport *a2)
{
  unsigned int v3; // ebx

  if ( a2 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)a2 + 12, 1, 0) )
    {
      v3 = -2147024726;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, 2147942570LL);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000e35c  push    rbx
0x18000e35e  sub     rsp, 20h
0x18000e362  mov     r8, rdx
0x18000e365  test    rdx, rdx
0x18000e368  jnz     short loc_18000E3A1
0x18000e36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e371  lea     rax, WPP_GLOBAL_Control
0x18000e378  cmp     rcx, rax
0x18000e37b  jz      short loc_18000E39A
0x18000e37d  lea     edx, [r8+1]
0x18000e381  test    [rcx+1Ch], dl
0x18000e384  jz      short loc_18000E39A
0x18000e386  mov     rcx, [rcx+10h]
0x18000e38a  lea     edx, [r8+15h]
0x18000e38e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e395  call    WPP_SF_
0x18000e39a  mov     eax, 80070057h
0x18000e39f  jmp     short loc_18000E3EE
0x18000e3a1  mov     edx, 1
0x18000e3a6  xor     eax, eax
0x18000e3a8  lock cmpxchg [r8+30h], edx
0x18000e3ae  jz      short loc_18000E3E7
0x18000e3b0  mov     ebx, 800700AAh
0x18000e3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3bc  lea     rax, WPP_GLOBAL_Control
0x18000e3c3  cmp     rcx, rax
0x18000e3c6  jz      short loc_18000E3EC
0x18000e3c8  test    [rcx+1Ch], dl
0x18000e3cb  jz      short loc_18000E3EC
0x18000e3cd  mov     rcx, [rcx+10h]
0x18000e3d1  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e3d8  mov     edx, 16h
0x18000e3dd  mov     r9d, ebx
0x18000e3e0  call    WPP_SF_d
0x18000e3e5  jmp     short loc_18000E3EC
0x18000e3e7  mov     [rcx], r8
0x18000e3ea  xor     ebx, ebx
0x18000e3ec  mov     eax, ebx
0x18000e3ee  add     rsp, 20h
0x18000e3f2  pop     rbx
0x18000e3f3  retn
```
