# FreeConfigurationPayloadBuffer

- ea: `0x1800011c0`
- end: `0x180001380`
- name: `FreeConfigurationPayloadBuffer`
- size: `448`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800011c0`
- `0x180001390`
- `0x180004420`
- `0x1800063a0`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800012c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800012c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800012d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800012d5`

## string_xrefs

- `0x18000123e`: `FreeConfigurationPayloadBuffer`
- `0x1800012f7`: `FreeConfigurationPayloadBuffer`

## pseudocode

```c
void __fastcall FreeConfigurationPayloadBuffer(_QWORD *a1)
{
  PVOID *v2; // rbx
  PVOID v3; // rcx
  __int64 v4; // rdx
  _QWORD *i; // rbx
  HANDLE ProcessHeap; // rax
  int v7; // [rsp+30h] [rbp-818h] BYREF
  char v8[2044]; // [rsp+34h] [rbp-814h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString((wchar_t *)&v7, L"Entered: %s", L"FreeConfigurationPayloadBuffer");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v7);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    for ( i = (_QWORD *)a1[1]; i; i = (_QWORD *)a1[1] )
    {
      a1[1] = *i;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, i);
    }
    MIDL_user_free(a1);
    if ( byte_1800167C1 < 0 )
    {
      LOWORD(v7) = 0;
      FormatRRASErrorString((wchar_t *)&v7, L"Leaving: %s", L"FreeConfigurationPayloadBuffer");
      if ( byte_1800167C1 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v7);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v3 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
      v4 = 48;
      goto LABEL_23;
    }
  }
  else if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v3 = v2[2];
    v4 = 47;
LABEL_23:
    WPP_SF_(v3, v4);
  }
}

```

## disassembly

```asm
0x1800011c0  mov     [rsp+arg_8], rbx
0x1800011c5  mov     [rsp+arg_10], rsi
0x1800011ca  push    rdi
0x1800011cb  sub     rsp, 840h
0x1800011d2  mov     rax, cs:__security_cookie
0x1800011d9  xor     rax, rsp
0x1800011dc  mov     [rsp+848h+var_18], rax
0x1800011e4  mov     rdi, rcx
0x1800011e7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800011ee  lea     rsi, WPP_GLOBAL_Control
0x1800011f5  cmp     rbx, rsi
0x1800011f8  jz      short loc_18000121B
0x1800011fa  test    byte ptr [rbx+1Ch], 1
0x1800011fe  jz      short loc_18000121B
0x180001200  cmp     byte ptr [rbx+19h], 6
0x180001204  jb      short loc_18000121B
0x180001206  mov     rcx, [rbx+10h]
0x18000120a  mov     edx, 2Eh ; '.'
0x18000120f  call    WPP_SF_
0x180001214  mov     rbx, cs:WPP_GLOBAL_Control
0x18000121b  xor     eax, eax
0x18000121d  lea     rcx, [rsp+848h+var_814]; void *
0x180001222  xor     edx, edx; Val
0x180001224  mov     [rsp+848h+var_818], eax
0x180001228  mov     r8d, 7FCh; Size
0x18000122e  call    memset_0
0x180001233  test    cs:byte_1800167C1, 80h
0x18000123a  jz      short loc_180001283
0x18000123c  xor     eax, eax
0x18000123e  lea     r8, aFreeconfigurat_0; "FreeConfigurationPayloadBuffer"
0x180001245  lea     rdx, aEnteredS; "Entered: %s"
0x18000124c  mov     word ptr [rsp+848h+var_818], ax
0x180001251  lea     rcx, [rsp+848h+var_818]
0x180001256  call    FormatRRASErrorString
0x18000125b  cmp     cs:byte_1800167C1, 0
0x180001262  jge     short loc_18000127C
0x180001264  lea     r8, [rsp+848h+var_818]
0x180001269  lea     rdx, RasVpnIkeApiTraceInfo
0x180001270  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001277  call    McTemplateU0z_EventWriteTransfer
0x18000127c  mov     rbx, cs:WPP_GLOBAL_Control
0x180001283  test    rdi, rdi
0x180001286  jnz     short loc_1800012B3
0x180001288  cmp     rbx, rsi
0x18000128b  jz      loc_18000135B
0x180001291  test    byte ptr [rbx+1Ch], 1
0x180001295  jz      loc_18000135B
0x18000129b  cmp     byte ptr [rbx+19h], 6
0x18000129f  jb      loc_18000135B
0x1800012a5  mov     rcx, [rbx+10h]
0x1800012a9  mov     edx, 2Fh ; '/'
0x1800012ae  jmp     loc_180001356
0x1800012b3  mov     rbx, [rdi+8]
0x1800012b7  test    rbx, rbx
0x1800012ba  jz      short loc_1800012E4
0x1800012bc  nop     dword ptr [rax+00h]
0x1800012c0  mov     rax, [rbx]
0x1800012c3  mov     [rdi+8], rax
0x1800012c7  call    cs:__imp_GetProcessHeap
0x1800012cd  mov     r8, rbx; lpMem
0x1800012d0  xor     edx, edx; dwFlags
0x1800012d2  mov     rcx, rax; hHeap
0x1800012d5  call    cs:__imp_HeapFree
0x1800012db  mov     rbx, [rdi+8]
0x1800012df  test    rbx, rbx
0x1800012e2  jnz     short loc_1800012C0
0x1800012e4  mov     rcx, rdi; void *
0x1800012e7  call    MIDL_user_free
0x1800012ec  test    cs:byte_1800167C1, 80h
0x1800012f3  jz      short loc_180001335
0x1800012f5  xor     eax, eax
0x1800012f7  lea     r8, aFreeconfigurat_0; "FreeConfigurationPayloadBuffer"
0x1800012fe  lea     rdx, aLeavingS; "Leaving: %s"
0x180001305  mov     word ptr [rsp+848h+var_818], ax
0x18000130a  lea     rcx, [rsp+848h+var_818]
0x18000130f  call    FormatRRASErrorString
0x180001314  cmp     cs:byte_1800167C1, 0
0x18000131b  jge     short loc_180001335
0x18000131d  lea     r8, [rsp+848h+var_818]
0x180001322  lea     rdx, RasVpnIkeApiTraceInfo
0x180001329  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001330  call    McTemplateU0z_EventWriteTransfer
0x180001335  mov     rcx, cs:WPP_GLOBAL_Control
0x18000133c  cmp     rcx, rsi
0x18000133f  jz      short loc_18000135B
0x180001341  test    byte ptr [rcx+1Ch], 1
0x180001345  jz      short loc_18000135B
0x180001347  cmp     byte ptr [rcx+19h], 6
0x18000134b  jb      short loc_18000135B
0x18000134d  mov     rcx, [rcx+10h]
0x180001351  mov     edx, 30h ; '0'
0x180001356  call    WPP_SF_
0x18000135b  mov     rcx, [rsp+848h+var_18]
0x180001363  xor     rcx, rsp; StackCookie
0x180001366  call    __security_check_cookie
0x18000136b  lea     r11, [rsp+848h+var_8]
0x180001373  mov     rbx, [r11+18h]
0x180001377  mov     rsi, [r11+20h]
0x18000137b  mov     rsp, r11
0x18000137e  pop     rdi
0x18000137f  retn
```
