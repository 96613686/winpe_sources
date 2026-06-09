# SMRemoveAllTriggers

- ea: `0x180043438`
- end: `0x180043559`
- name: `SMRemoveAllTriggers`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007d138`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180043438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043495`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043495`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043512`
- `MobileNetworking!FreeMemory` at `0x1800434db`
- `MobileNetworking!FreeMemory` at `0x1800434f9`
- `MobileNetworking!FreeMemory` at `0x1800434db`
- `MobileNetworking!FreeMemory` at `0x1800434f9`

## string_xrefs

- `0x1800434d4`: `SMRemoveAllTriggers`
- `0x1800434ed`: `SMRemoveAllTriggers`

## pseudocode

```c
void __fastcall SMRemoveAllTriggers(__int64 a1)
{
  PVOID *v2; // rcx
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    while ( 1 )
    {
      v3 = *(_QWORD **)a1;
      if ( *(_QWORD *)a1 == a1 )
        break;
      if ( v3[1] != a1 || (v4 = *v3, *(_QWORD **)(*v3 + 8LL) != v3) )
        __fastfail(3u);
      *(_QWORD *)a1 = v4;
      *(_QWORD *)(v4 + 8) = a1;
      v5 = v3;
      if ( v3[3] )
        FreeMemory(v3 + 3, "SMRemoveAllTriggers", 658);
      FreeMemory(&v5, "SMRemoveAllTriggers", 660);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_d(v2[2], 52, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids, 0);
}

```

## disassembly

```asm
0x180043438  mov     [rsp+arg_8], rbx
0x18004343d  mov     [rsp+arg_10], rsi
0x180043442  push    rdi
0x180043443  sub     rsp, 20h
0x180043447  mov     rbx, rcx
0x18004344a  mov     [rsp+28h+arg_0], 0
0x180043453  mov     rcx, cs:WPP_GLOBAL_Control
0x18004345a  lea     rsi, WPP_GLOBAL_Control
0x180043461  cmp     rcx, rsi
0x180043464  jz      short loc_180043488
0x180043466  test    byte ptr [rcx+1Ch], 1
0x18004346a  jz      short loc_180043488
0x18004346c  mov     rcx, [rcx+10h]
0x180043470  lea     r8, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids
0x180043477  mov     edx, 33h ; '3'
0x18004347c  call    WPP_SF_
0x180043481  mov     rcx, cs:WPP_GLOBAL_Control
0x180043488  test    rbx, rbx
0x18004348b  jz      loc_180043525
0x180043491  lea     rcx, [rbx+18h]; lpCriticalSection
0x180043495  call    cs:__imp_EnterCriticalSection
0x18004349c  nop     dword ptr [rax+rax+00h]
0x1800434a1  mov     rax, [rbx]
0x1800434a4  cmp     rax, rbx
0x1800434a7  jz      short loc_18004350E
0x1800434a9  cmp     [rax+8], rbx
0x1800434ad  jnz     short loc_180043507
0x1800434af  mov     rcx, [rax]
0x1800434b2  cmp     [rcx+8], rax
0x1800434b6  jnz     short loc_180043507
0x1800434b8  mov     [rbx], rcx
0x1800434bb  mov     [rcx+8], rbx
0x1800434bf  lea     rcx, [rax+18h]
0x1800434c3  mov     [rsp+28h+arg_0], rax
0x1800434c8  cmp     qword ptr [rcx], 0
0x1800434cc  jz      short loc_1800434E7
0x1800434ce  mov     r8d, 292h
0x1800434d4  lea     rdx, aSmremovealltri; "SMRemoveAllTriggers"
0x1800434db  call    cs:__imp_FreeMemory
0x1800434e2  nop     dword ptr [rax+rax+00h]
0x1800434e7  mov     r8d, 294h
0x1800434ed  lea     rdx, aSmremovealltri; "SMRemoveAllTriggers"
0x1800434f4  lea     rcx, [rsp+28h+arg_0]
0x1800434f9  call    cs:__imp_FreeMemory
0x180043500  nop     dword ptr [rax+rax+00h]
0x180043505  jmp     short loc_1800434A1
0x180043507  mov     ecx, 3
0x18004350c  int     29h; Win8: RtlFailFast(ecx)
0x18004350e  lea     rcx, [rbx+18h]; lpCriticalSection
0x180043512  call    cs:__imp_LeaveCriticalSection
0x180043519  nop     dword ptr [rax+rax+00h]
0x18004351e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043525  cmp     rcx, rsi
0x180043528  jz      short loc_180043548
0x18004352a  test    byte ptr [rcx+1Ch], 1
0x18004352e  jz      short loc_180043548
0x180043530  mov     rcx, [rcx+10h]
0x180043534  lea     r8, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids
0x18004353b  mov     edx, 34h ; '4'
0x180043540  xor     r9d, r9d
0x180043543  call    WPP_SF_d
0x180043548  mov     rbx, [rsp+28h+arg_8]
0x18004354d  mov     rsi, [rsp+28h+arg_10]
0x180043552  add     rsp, 20h
0x180043556  pop     rdi
0x180043557  retn
```
