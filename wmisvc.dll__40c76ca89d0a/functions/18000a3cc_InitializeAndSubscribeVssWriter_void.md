# InitializeAndSubscribeVssWriter(void)

- ea: `0x18000a3cc`
- end: `0x18000a50f`
- name: `?InitializeAndSubscribeVssWriter@@YAHXZ`
- size: `323`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800052a0`
- `0x180008840`

## callees

- `0x18000a3cc`
- `0x18000a518`
- `0x18000b648`
- `0x18000c5cc`
- `0x180020010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a3eb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a3eb`

## pseudocode

```c
_BOOL8 InitializeAndSubscribeVssWriter(void)
{
  CWbemVssWriter *v0; // rax
  int v2; // ebx
  __int64 v3; // rcx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int128 v6; // [rsp+50h] [rbp-18h] BYREF

  HIBYTE(word_180032CD8) = 1;
  if ( dword_180032A50 )
    return 1;
  v0 = (CWbemVssWriter *)CWin32DefaultArena::WbemMemAlloc(0x48u);
  if ( v0 )
    v0 = CWbemVssWriter::CWbemVssWriter(v0);
  qword_180032CD0 = (__int64)v0;
  if ( v0 )
  {
    v6 = xmmword_180025968;
    v2 = CVssWriter::Initialize((__int64)v0, &v6);
    if ( v2 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        return v2 >= 0;
      }
      v5 = 21;
    }
    else
    {
      v3 = *(_QWORD *)(qword_180032CD0 + 8);
      if ( v3 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v3 + 32LL))(v3, 0, 6);
        if ( v2 >= 0 )
        {
          LOBYTE(word_180032CD8) = 1;
          return v2 >= 0;
        }
      }
      else
      {
        v2 = -2147467259;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        return v2 >= 0;
      }
      v5 = 20;
    }
    WPP_SF_(v4[2], v5, WPP_2716f4bd31e130f967505b342dce5479_Traceguids);
    return v2 >= 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2716f4bd31e130f967505b342dce5479_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a3cc  push    rbx
0x18000a3ce  sub     rsp, 60h
0x18000a3d2  mov     byte ptr cs:word_180032CD8+1, 1
0x18000a3d9  cmp     cs:dword_180032A50, 0
0x18000a3e0  jnz     loc_18000A504
0x18000a3e6  mov     ecx, 48h ; 'H'
0x18000a3eb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a3f1  mov     [rsp+68h+arg_0], rax
0x18000a3f6  test    rax, rax
0x18000a3f9  jz      short loc_18000A404
0x18000a3fb  mov     rcx, rax; this
0x18000a3fe  call    ??0CWbemVssWriter@@QEAA@XZ; CWbemVssWriter::CWbemVssWriter(void)
0x18000a403  nop
0x18000a404  mov     cs:qword_180032CD0, rax
0x18000a40b  test    rax, rax
0x18000a40e  jnz     short loc_18000A44B
0x18000a410  lea     rax, WPP_GLOBAL_Control
0x18000a417  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a41e  cmp     rcx, rax
0x18000a421  jz      short loc_18000A444
0x18000a423  test    byte ptr [rcx+1Ch], 1
0x18000a427  jz      short loc_18000A444
0x18000a429  cmp     byte ptr [rcx+19h], 5
0x18000a42d  jb      short loc_18000A444
0x18000a42f  mov     edx, 13h
0x18000a434  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x18000a43b  mov     rcx, [rcx+10h]
0x18000a43f  call    WPP_SF_
0x18000a444  xor     eax, eax
0x18000a446  jmp     loc_18000A509
0x18000a44b  movups  xmm0, cs:xmmword_180025968
0x18000a452  movdqu  [rsp+68h+var_18], xmm0
0x18000a458  lea     rdx, [rsp+68h+var_18]
0x18000a45d  mov     rcx, rax
0x18000a460  call    ?Initialize@CVssWriter@@QEAAJU_GUID@@PEBGW4VSS_USAGE_TYPE@@W4VSS_SOURCE_TYPE@@W4_VSS_APPLICATION_LEVEL@@KW4VSS_ALTERNATE_WRITER_STATE@@_N1@Z; CVssWriter::Initialize(_GUID,ushort const *,VSS_USAGE_TYPE,VSS_SOURCE_TYPE,_VSS_APPLICATION_LEVEL,ulong,VSS_ALTERNATE_WRITER_STATE,bool,ushort const *)
0x18000a465  mov     ebx, eax
0x18000a467  test    eax, eax
0x18000a469  js      short loc_18000A4C7
0x18000a46b  mov     rax, cs:qword_180032CD0
0x18000a472  mov     rcx, [rax+8]
0x18000a476  test    rcx, rcx
0x18000a479  jnz     short loc_18000A4A6
0x18000a47b  mov     ebx, 80004005h
0x18000a480  lea     rax, WPP_GLOBAL_Control
0x18000a487  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a48e  cmp     rcx, rax
0x18000a491  jz      short loc_18000A4FB
0x18000a493  test    byte ptr [rcx+1Ch], 1
0x18000a497  jz      short loc_18000A4FB
0x18000a499  cmp     byte ptr [rcx+19h], 5
0x18000a49d  jb      short loc_18000A4FB
0x18000a49f  mov     edx, 14h
0x18000a4a4  jmp     short loc_18000A4EB
0x18000a4a6  mov     rax, [rcx]
0x18000a4a9  xor     edx, edx
0x18000a4ab  lea     r8d, [rdx+6]
0x18000a4af  mov     rax, [rax+20h]
0x18000a4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b8  mov     ebx, eax
0x18000a4ba  test    eax, eax
0x18000a4bc  js      short loc_18000A480
0x18000a4be  mov     byte ptr cs:word_180032CD8, 1
0x18000a4c5  jmp     short loc_18000A4FB
0x18000a4c7  lea     rax, WPP_GLOBAL_Control
0x18000a4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4d5  cmp     rcx, rax
0x18000a4d8  jz      short loc_18000A4FB
0x18000a4da  test    byte ptr [rcx+1Ch], 1
0x18000a4de  jz      short loc_18000A4FB
0x18000a4e0  cmp     byte ptr [rcx+19h], 5
0x18000a4e4  jb      short loc_18000A4FB
0x18000a4e6  mov     edx, 15h
0x18000a4eb  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x18000a4f2  mov     rcx, [rcx+10h]
0x18000a4f6  call    WPP_SF_
0x18000a4fb  not     ebx
0x18000a4fd  shr     ebx, 1Fh
0x18000a500  mov     eax, ebx
0x18000a502  jmp     short loc_18000A509
0x18000a504  mov     eax, 1
0x18000a509  add     rsp, 60h
0x18000a50d  pop     rbx
0x18000a50e  retn
```
