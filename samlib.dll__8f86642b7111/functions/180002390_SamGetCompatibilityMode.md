# SamGetCompatibilityMode

- ea: `0x180002390`
- end: `0x18000251e`
- name: `SamGetCompatibilityMode`
- size: `398`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002390`
- `0x180003220`
- `0x180006160`
- `0x18000807c`
- `0x18000c210`
- `0x180014a50`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023df`

## pseudocode

```c
__int64 __fastcall SamGetCompatibilityMode(void **a1, int *a2)
{
  unsigned __int16 *CallingProcessInfo; // rax
  __int64 v5; // rcx
  unsigned __int16 *v6; // rsi
  const wchar_t *v7; // r9
  __int64 v8; // rcx
  PVOID v9; // rcx
  int v11; // eax
  __int64 v12; // r9
  PVOID v13; // rcx

  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v6 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v7 = L"<unknown>";
      if ( CallingProcessInfo )
        v7 = CallingProcessInfo;
      McTemplateU0pz_EventWriteTransfer(v5, (const EVENT_DESCRIPTOR *)SamGetCompatibilityModeEntry, (__int64)a1, v7);
    }
    LocalFree(v6);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( !(unsigned __int8)SampIsValidClientHandle(a1, 0) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dq_EventWriteTransfer(
        (__int64)v9,
        (const EVENT_DESCRIPTOR *)SamGetCompatibilityModeExit,
        3221225480LL,
        0);
    return 3221225480LL;
  }
  if ( !a2 )
  {
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dq_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)SamGetCompatibilityModeExit, 3221225485LL, 0);
    return 3221225485LL;
  }
  *a2 = 0;
  v11 = *((_DWORD *)a1 + 3);
  if ( (v11 & 2) != 0 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( (v11 & 4) == 0 )
      goto LABEL_26;
    v12 = 2;
  }
  *a2 = v12;
LABEL_26:
  v13 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 330, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v12);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dq_EventWriteTransfer((__int64)v13, (const EVENT_DESCRIPTOR *)SamGetCompatibilityModeExit, 0, *a2);
  return 0;
}

```

## disassembly

```asm
0x180002390  mov     [rsp+arg_8], rbx
0x180002395  push    rdi
0x180002396  sub     rsp, 20h
0x18000239a  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800023a1  mov     rbx, rdx
0x1800023a4  mov     rdi, rcx
0x1800023a7  jz      short loc_1800023EA
0x1800023a9  mov     [rsp+28h+arg_0], rsi
0x1800023ae  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800023b3  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800023ba  mov     rsi, rax
0x1800023bd  jz      short loc_1800023DC
0x1800023bf  test    rax, rax
0x1800023c2  lea     r9, aUnknown; "<unknown>"
0x1800023c9  mov     r8, rdi
0x1800023cc  lea     rdx, SamGetCompatibilityModeEntry
0x1800023d3  cmovnz  r9, rax
0x1800023d7  call    McTemplateU0pz_EventWriteTransfer
0x1800023dc  mov     rcx, rsi; hMem
0x1800023df  call    cs:__imp_LocalFree
0x1800023e5  mov     rsi, [rsp+28h+arg_0]
0x1800023ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023f1  test    byte ptr [rcx+1Ch], 2
0x1800023f5  jz      short loc_180002415
0x1800023f7  cmp     byte ptr [rcx+19h], 4
0x1800023fb  jb      short loc_180002415
0x1800023fd  mov     rcx, [rcx+10h]
0x180002401  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180002408  mov     edx, 148h
0x18000240d  mov     r9, rdi
0x180002410  call    WPP_SF_q
0x180002415  xor     edx, edx; void **
0x180002417  mov     rcx, rdi; void *
0x18000241a  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000241f  test    al, al
0x180002421  jnz     short loc_180002476
0x180002423  mov     rcx, cs:WPP_GLOBAL_Control
0x18000242a  test    byte ptr [rcx+1Ch], 2
0x18000242e  jz      short loc_18000244E
0x180002430  cmp     byte ptr [rcx+19h], 2
0x180002434  jb      short loc_18000244E
0x180002436  mov     rcx, [rcx+10h]
0x18000243a  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180002441  mov     edx, 149h
0x180002446  mov     r9, rdi
0x180002449  call    WPP_SF_q
0x18000244e  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002455  jz      short loc_18000246C
0x180002457  xor     r9d, r9d
0x18000245a  lea     rdx, SamGetCompatibilityModeExit
0x180002461  mov     r8d, 0C0000008h
0x180002467  call    McTemplateU0dq_EventWriteTransfer
0x18000246c  mov     eax, 0C0000008h
0x180002471  jmp     loc_180002513
0x180002476  test    rbx, rbx
0x180002479  jnz     short loc_1800024A9
0x18000247b  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002482  jz      short loc_180002499
0x180002484  xor     r9d, r9d
0x180002487  lea     rdx, SamGetCompatibilityModeExit
0x18000248e  mov     r8d, 0C000000Dh
0x180002494  call    McTemplateU0dq_EventWriteTransfer
0x180002499  mov     eax, 0C000000Dh
0x18000249e  mov     rbx, [rsp+28h+arg_8]
0x1800024a3  add     rsp, 20h
0x1800024a7  pop     rdi
0x1800024a8  retn
0x1800024a9  mov     dword ptr [rbx], 0
0x1800024af  mov     eax, [rdi+0Ch]
0x1800024b2  test    al, 2
0x1800024b4  jz      short loc_1800024BE
0x1800024b6  mov     r9d, 1
0x1800024bc  jmp     short loc_1800024CB
0x1800024be  xor     r9d, r9d
0x1800024c1  test    al, 4
0x1800024c3  jz      short loc_1800024CE
0x1800024c5  mov     r9d, 2
0x1800024cb  mov     [rbx], r9d
0x1800024ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024d5  test    byte ptr [rcx+1Ch], 2
0x1800024d9  jz      short loc_1800024F6
0x1800024db  cmp     byte ptr [rcx+19h], 4
0x1800024df  jb      short loc_1800024F6
0x1800024e1  mov     rcx, [rcx+10h]
0x1800024e5  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800024ec  mov     edx, 14Ah
0x1800024f1  call    WPP_SF_D
0x1800024f6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800024fd  jz      short loc_180002511
0x1800024ff  mov     r9d, [rbx]
0x180002502  lea     rdx, SamGetCompatibilityModeExit
0x180002509  xor     r8d, r8d
0x18000250c  call    McTemplateU0dq_EventWriteTransfer
0x180002511  xor     eax, eax
0x180002513  mov     rbx, [rsp+28h+arg_8]
0x180002518  add     rsp, 20h
0x18000251c  pop     rdi
0x18000251d  retn
```
