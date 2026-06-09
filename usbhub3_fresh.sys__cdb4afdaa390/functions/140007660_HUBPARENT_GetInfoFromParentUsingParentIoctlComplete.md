# HUBPARENT_GetInfoFromParentUsingParentIoctlComplete

- ea: `0x140007660`
- end: `0x140007809`
- name: `HUBPARENT_GetInfoFromParentUsingParentIoctlComplete`
- size: `425`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x140007660`
- `0x14000a53c`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
__int64 __fastcall HUBPARENT_GetInfoFromParentUsingParentIoctlComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // rbx
  _QWORD *v11; // rdi
  int v12; // edx
  _QWORD v14[23]; // [rsp+30h] [rbp-B8h] BYREF

  memset(v14, 0, 0x88u);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1392))(WdfDriverGlobals, a2);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v6,
         off_14006B270);
  v8 = *(_DWORD *)(a3 + 8);
  v9 = v7;
  if ( v8 >= 0 )
  {
    v10 = *(_QWORD *)(v7 + 2464);
    memset(v14, 0, 0x88u);
    v11 = (_QWORD *)(v9 + 32);
    v14[0] = 0x100000088LL;
    v14[4] = v10;
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64))(WdfFunctions_01015 + 1336))(
           WdfDriverGlobals,
           *(_QWORD *)(v9 + 16),
           0,
           v9 + 32);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD *))(WdfFunctions_01015 + 1344))(
             WdfDriverGlobals,
             *v11,
             v14);
      if ( v8 >= 0 )
      {
        if ( (*(_DWORD *)(v9 + 2512) & 1) != 0 )
          _InterlockedOr((volatile signed __int32 *)(v9 + 40), 0x8000u);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v9 + 2536),
            v12,
            3,
            21,
            (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids,
            v8);
        }
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *v11);
      }
    }
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
  return HUBSM_AddEvent(v9 + 1280, ((v8 >> 31) & 0xFFFFFFFC) + 2042);
}

```

## disassembly

```asm
0x140007660  push    rbx
0x140007662  push    rbp
0x140007663  push    rsi
0x140007664  push    rdi
0x140007665  sub     rsp, 0C8h
0x14000766c  mov     rdi, r8
0x14000766f  mov     rbx, rdx
0x140007672  mov     rbp, rcx
0x140007675  xor     edx, edx; Val
0x140007677  mov     r8d, 88h; Size
0x14000767d  lea     rcx, [rsp+0E8h+var_B8]; void *
0x140007682  call    memset
0x140007687  mov     rax, cs:WdfFunctions_01015
0x14000768e  mov     rdx, rbx
0x140007691  mov     rcx, cs:WdfDriverGlobals
0x140007698  mov     rax, [rax+570h]
0x14000769f  call    _guard_dispatch_icall
0x1400076a4  mov     rcx, cs:WdfFunctions_01015
0x1400076ab  mov     rdx, rax
0x1400076ae  mov     r8, cs:off_14006B270
0x1400076b5  mov     rax, [rcx+650h]
0x1400076bc  mov     rcx, cs:WdfDriverGlobals
0x1400076c3  call    _guard_dispatch_icall
0x1400076c8  mov     ebx, [rdi+8]
0x1400076cb  mov     rsi, rax
0x1400076ce  test    ebx, ebx
0x1400076d0  js      loc_1400077C7
0x1400076d6  mov     rbx, [rax+9A0h]
0x1400076dd  lea     rcx, [rsp+0E8h+var_B8]; void *
0x1400076e2  xor     edx, edx; Val
0x1400076e4  mov     r8d, 88h; Size
0x1400076ea  call    memset
0x1400076ef  mov     rax, cs:WdfFunctions_01015
0x1400076f6  lea     rdi, [rsi+20h]
0x1400076fa  mov     rcx, cs:WdfDriverGlobals
0x140007701  mov     r9, rdi
0x140007704  mov     [rsp+0E8h+var_B8], 88h
0x14000770c  xor     r8d, r8d
0x14000770f  mov     [rsp+0E8h+var_B4], 1
0x140007717  mov     [rsp+0E8h+var_98], rbx
0x14000771c  mov     rax, [rax+538h]
0x140007723  mov     rdx, [rsi+10h]
0x140007727  call    _guard_dispatch_icall
0x14000772c  mov     ebx, eax
0x14000772e  test    eax, eax
0x140007730  js      loc_1400077C7
0x140007736  mov     rax, cs:WdfFunctions_01015
0x14000773d  lea     r8, [rsp+0E8h+var_B8]
0x140007742  mov     rdx, [rdi]
0x140007745  mov     rcx, cs:WdfDriverGlobals
0x14000774c  mov     rax, [rax+540h]
0x140007753  call    _guard_dispatch_icall
0x140007758  mov     ebx, eax
0x14000775a  test    eax, eax
0x14000775c  jns     short loc_1400077B5
0x14000775e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007765  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000776c  jz      short loc_140007796
0x14000776e  mov     rcx, [rsi+9E8h]
0x140007775  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x14000777c  mov     r9d, 15h
0x140007782  mov     [rsp+0E8h+var_C0], ebx
0x140007786  mov     dl, 2
0x140007788  mov     [rsp+0E8h+var_C8], rax
0x14000778d  lea     r8d, [r9-12h]
0x140007791  call    WPP_RECORDER_SF_d
0x140007796  mov     rax, cs:WdfFunctions_01015
0x14000779d  mov     rdx, [rdi]
0x1400077a0  mov     rcx, cs:WdfDriverGlobals
0x1400077a7  mov     rax, [rax+680h]
0x1400077ae  call    _guard_dispatch_icall
0x1400077b3  jmp     short loc_1400077C7
0x1400077b5  mov     eax, [rsi+9D0h]
0x1400077bb  test    al, 1
0x1400077bd  jz      short loc_1400077C7
0x1400077bf  lock or dword ptr [rsi+28h], 8000h
0x1400077c7  mov     rax, cs:WdfFunctions_01015
0x1400077ce  mov     rdx, rbp
0x1400077d1  mov     rcx, cs:WdfDriverGlobals
0x1400077d8  mov     rax, [rax+680h]
0x1400077df  call    _guard_dispatch_icall
0x1400077e4  sar     ebx, 1Fh
0x1400077e7  lea     rcx, [rsi+500h]
0x1400077ee  and     ebx, 0FFFFFFFCh
0x1400077f1  lea     edx, [rbx+7FAh]
0x1400077f7  call    HUBSM_AddEvent
0x1400077fc  add     rsp, 0C8h
0x140007803  pop     rdi
0x140007804  pop     rsi
0x140007805  pop     rbp
0x140007806  pop     rbx
0x140007807  retn
```
