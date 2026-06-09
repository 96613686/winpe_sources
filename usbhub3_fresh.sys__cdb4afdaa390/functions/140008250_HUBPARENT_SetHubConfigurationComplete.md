# HUBPARENT_SetHubConfigurationComplete

- ea: `0x140008250`
- end: `0x1400083ad`
- name: `HUBPARENT_SetHubConfigurationComplete`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x140008250`
- `0x14000a53c`
- `0x140045570`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008379`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008379`

## pseudocode

```c
__int64 __fastcall HUBPARENT_SetHubConfigurationComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // edx
  int v10; // ebx
  int v11; // ebp
  __int64 v12; // rdi
  unsigned int v13; // eax
  unsigned int v15; // [rsp+28h] [rbp-50h]

  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1392))(WdfDriverGlobals);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v7,
         off_14006B270);
  v10 = *(_DWORD *)(a3 + 8);
  v11 = *(_DWORD *)(a4 + 4);
  v12 = v8;
  if ( v10 < 0 )
    goto LABEL_9;
  *(_QWORD *)(v8 + 1120) = *(_QWORD *)(a4 + 72);
  *(_QWORD *)(v8 + 80) = *(_QWORD *)(a4 + 32);
  v13 = *(unsigned __int16 *)(a4 + 64);
  *(_WORD *)(v12 + 88) = v13;
  if ( *(_WORD *)(v12 + 2474) >= 0x300u )
  {
    if ( v13 <= 2 )
    {
      if ( v13 == 2 )
        goto LABEL_11;
    }
    else
    {
      v10 = -1073741216;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = v13;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v12 + 2536),
        v9,
        3,
        10,
        (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids,
        v15);
    }
    if ( v10 < 0 )
    {
LABEL_9:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(v12 + 2536),
          v9,
          3,
          11,
          (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids,
          v10,
          v11);
      }
    }
  }
LABEL_11:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
  ExFreePoolWithTag((PVOID)a4, 0);
  return HUBSM_AddEvent(v12 + 1280, ((v10 >> 31) & 0xFFFFFFFC) + 2010);
}

```

## disassembly

```asm
0x140008250  push    rbx
0x140008252  push    rbp
0x140008253  push    rsi
0x140008254  push    rdi
0x140008255  push    r13
0x140008257  push    r14
0x140008259  push    r15
0x14000825b  sub     rsp, 40h
0x14000825f  mov     rax, cs:WdfFunctions_01015
0x140008266  mov     r14, rcx
0x140008269  mov     rcx, cs:WdfDriverGlobals
0x140008270  mov     rsi, r9
0x140008273  mov     rbx, r8
0x140008276  mov     rax, [rax+570h]
0x14000827d  call    _guard_dispatch_icall
0x140008282  mov     rdx, cs:WdfFunctions_01015
0x140008289  mov     r10, rax
0x14000828c  mov     r8, cs:off_14006B270
0x140008293  mov     rcx, cs:WdfDriverGlobals
0x14000829a  mov     rax, [rdx+650h]
0x1400082a1  mov     rdx, r10
0x1400082a4  call    _guard_dispatch_icall
0x1400082a9  mov     ebx, [rbx+8]
0x1400082ac  lea     r15, WPP_RECORDER_INITIALIZED
0x1400082b3  mov     ebp, [rsi+4]
0x1400082b6  mov     rdi, rax
0x1400082b9  lea     r13, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x1400082c0  test    ebx, ebx
0x1400082c2  js      short loc_140008329
0x1400082c4  mov     rcx, [rsi+48h]
0x1400082c8  mov     [rax+460h], rcx
0x1400082cf  mov     rcx, [rsi+20h]
0x1400082d3  mov     [rax+50h], rcx
0x1400082d7  mov     ecx, 300h
0x1400082dc  movzx   eax, word ptr [rsi+40h]
0x1400082e0  mov     [rdi+58h], ax
0x1400082e4  cmp     [rdi+9AAh], cx
0x1400082eb  jb      short loc_140008357
0x1400082ed  cmp     eax, 2
0x1400082f0  jbe     short loc_1400082F9
0x1400082f2  mov     ebx, 0C0000260h
0x1400082f7  jmp     short loc_1400082FB
0x1400082f9  jz      short loc_140008357
0x1400082fb  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140008302  jz      short loc_140008325
0x140008304  mov     rcx, [rdi+9E8h]
0x14000830b  mov     r9d, 0Ah
0x140008311  mov     [rsp+78h+var_50], eax
0x140008315  mov     dl, 2
0x140008317  mov     [rsp+78h+var_58], r13
0x14000831c  lea     r8d, [r9-7]
0x140008320  call    WPP_RECORDER_SF_d
0x140008325  test    ebx, ebx
0x140008327  jns     short loc_140008357
0x140008329  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140008330  jz      short loc_140008357
0x140008332  mov     rcx, [rdi+9E8h]
0x140008339  mov     r9d, 0Bh
0x14000833f  mov     [rsp+78h+var_48], ebp
0x140008343  mov     dl, 2
0x140008345  mov     [rsp+78h+var_50], ebx
0x140008349  mov     [rsp+78h+var_58], r13
0x14000834e  lea     r8d, [r9-8]
0x140008352  call    WPP_RECORDER_SF_dD
0x140008357  mov     rax, cs:WdfFunctions_01015
0x14000835e  mov     rdx, r14
0x140008361  mov     rcx, cs:WdfDriverGlobals
0x140008368  mov     rax, [rax+680h]
0x14000836f  call    _guard_dispatch_icall
0x140008374  xor     edx, edx; Tag
0x140008376  mov     rcx, rsi; P
0x140008379  call    cs:__imp_ExFreePoolWithTag
0x140008380  nop     dword ptr [rax+rax+00h]
0x140008385  sar     ebx, 1Fh
0x140008388  lea     rcx, [rdi+500h]
0x14000838f  and     ebx, 0FFFFFFFCh
0x140008392  lea     edx, [rbx+7DAh]
0x140008398  call    HUBSM_AddEvent
0x14000839d  add     rsp, 40h
0x1400083a1  pop     r15
0x1400083a3  pop     r14
0x1400083a5  pop     r13
0x1400083a7  pop     rdi
0x1400083a8  pop     rsi
0x1400083a9  pop     rbp
0x1400083aa  pop     rbx
0x1400083ab  retn
```
