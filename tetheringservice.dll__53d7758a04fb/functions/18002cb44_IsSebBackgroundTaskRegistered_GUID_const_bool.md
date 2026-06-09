# IsSebBackgroundTaskRegistered(_GUID const &,bool *)

- ea: `0x18002cb44`
- end: `0x18002cd41`
- name: `?IsSebBackgroundTaskRegistered@@YAJAEBU_GUID@@PEA_N@Z`
- size: `509`
- prototype: `__int64 __fastcall(const struct _GUID *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dfd8`
- `0x18002d868`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18002cb44`
- `0x18002ddf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cbf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cbf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc0b`
- `SystemEventsBrokerClient!SebQueryEventData` at `0x18002cc43`
- `SystemEventsBrokerClient!SebQueryEventData` at `0x18002cc43`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18002cbcf`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18002cbcf`

## pseudocode

```c
__int64 __fastcall IsSebBackgroundTaskRegistered(const struct _GUID *a1, bool *a2)
{
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // r8
  __int64 v7; // r12
  _QWORD *v8; // rsi
  void *v9; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  TetheringServiceTelemetry *v12; // rcx
  __int64 v13; // rdx
  void *v14; // rbx
  HANDLE v15; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-40h] BYREF
  __int128 v18; // [rsp+40h] [rbp-30h] BYREF
  __int128 p_lpMem; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
  }
  *a2 = 0;
  lpMem = 0;
  p_lpMem = (unsigned __int64)&lpMem;
  LOBYTE(v20) = 1;
  v18 = (__int128)*a1;
  v5 = SebQueryEventPackage(&v18, (char *)&p_lpMem + 8);
  if ( (_BYTE)v20 )
  {
    v7 = *((_QWORD *)&p_lpMem + 1);
    v8 = (_QWORD *)p_lpMem;
    v9 = *(void **)p_lpMem;
    if ( *(_QWORD *)p_lpMem )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
      SetLastError(LastError);
    }
    *v8 = v7;
  }
  if ( v5 >= 0 )
  {
    p_lpMem = 0;
    v20 = 0;
    v18 = (__int128)*a1;
    v5 = SebQueryEventData(&v18, &p_lpMem, lpMem);
    if ( v5 < 0 )
    {
LABEL_23:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    if ( DWORD2(p_lpMem) == 68 )
    {
      *a2 = 1;
      goto LABEL_23;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v13 = 67;
LABEL_15:
    WPP_SF_(*((_QWORD *)v12 + 2), v13, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
    goto LABEL_23;
  }
  if ( v5 == -2147024894 )
  {
    v5 = 0;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_24;
    v13 = 68;
    goto LABEL_15;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids,
      (unsigned int)v5);
    goto LABEL_23;
  }
LABEL_24:
  if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_dc(*((_QWORD *)v12 + 2), v4, v6, (unsigned int)v5, *a2);
LABEL_27:
  v14 = lpMem;
  if ( lpMem )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002cb44  mov     [rsp-38h+arg_10], rbx
0x18002cb49  push    rbp
0x18002cb4a  push    rsi
0x18002cb4b  push    rdi
0x18002cb4c  push    r12
0x18002cb4e  push    r13
0x18002cb50  push    r14
0x18002cb52  push    r15
0x18002cb54  mov     rbp, rsp
0x18002cb57  sub     rsp, 70h
0x18002cb5b  mov     rax, cs:__security_cookie
0x18002cb62  xor     rax, rsp
0x18002cb65  mov     [rbp+var_8], rax
0x18002cb69  mov     r15, rdx
0x18002cb6c  mov     r13, rcx
0x18002cb6f  lea     rbx, WPP_GLOBAL_Control
0x18002cb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb7d  cmp     rcx, rbx
0x18002cb80  jz      short loc_18002CB9D
0x18002cb82  test    byte ptr [rcx+1Ch], 8
0x18002cb86  jz      short loc_18002CB9D
0x18002cb88  mov     edx, 42h ; 'B'
0x18002cb8d  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002cb94  mov     rcx, [rcx+10h]
0x18002cb98  call    WPP_SF_
0x18002cb9d  mov     byte ptr [r15], 0
0x18002cba1  mov     [rbp+lpMem], 0
0x18002cba9  lea     rax, [rbp+lpMem]
0x18002cbad  mov     qword ptr [rbp+var_20], rax
0x18002cbb1  mov     qword ptr [rbp+var_20+8], 0
0x18002cbb9  mov     byte ptr [rbp+var_10], 1
0x18002cbbd  movups  xmm0, xmmword ptr [r13+0]
0x18002cbc2  movdqu  [rbp+var_30], xmm0
0x18002cbc7  lea     rdx, [rbp+var_20+8]
0x18002cbcb  lea     rcx, [rbp+var_30]
0x18002cbcf  call    cs:__imp_SebQueryEventPackage
0x18002cbd5  mov     edi, eax
0x18002cbd7  cmp     byte ptr [rbp+var_10], 0
0x18002cbdb  jz      short loc_18002CC1C
0x18002cbdd  mov     r12, qword ptr [rbp+var_20+8]
0x18002cbe1  mov     rsi, qword ptr [rbp+var_20]
0x18002cbe5  mov     r14, [rsi]
0x18002cbe8  test    r14, r14
0x18002cbeb  jz      short loc_18002CC19
0x18002cbed  call    cs:__imp_GetLastError
0x18002cbf3  mov     ebx, eax
0x18002cbf5  call    cs:__imp_GetProcessHeap
0x18002cbfb  mov     rcx, rax; hHeap
0x18002cbfe  mov     r8, r14; lpMem
0x18002cc01  xor     edx, edx; dwFlags
0x18002cc03  call    cs:__imp_HeapFree
0x18002cc09  mov     ecx, ebx; dwErrCode
0x18002cc0b  call    cs:__imp_SetLastError
0x18002cc11  nop
0x18002cc12  lea     rbx, WPP_GLOBAL_Control
0x18002cc19  mov     [rsi], r12
0x18002cc1c  test    edi, edi
0x18002cc1e  js      short loc_18002CC8C
0x18002cc20  xorps   xmm0, xmm0
0x18002cc23  xor     eax, eax
0x18002cc25  movups  [rbp+var_20], xmm0
0x18002cc29  mov     [rbp+var_10], rax
0x18002cc2d  movups  xmm0, xmmword ptr [r13+0]
0x18002cc32  movdqu  [rbp+var_30], xmm0
0x18002cc37  mov     r8, [rbp+lpMem]
0x18002cc3b  lea     rdx, [rbp+var_20]
0x18002cc3f  lea     rcx, [rbp+var_30]
0x18002cc43  call    cs:__imp_SebQueryEventData
0x18002cc49  mov     edi, eax
0x18002cc4b  test    eax, eax
0x18002cc4d  js      loc_18002CCD7
0x18002cc53  cmp     dword ptr [rbp+var_20+8], 44h ; 'D'
0x18002cc57  jnz     short loc_18002CC5F
0x18002cc59  mov     byte ptr [r15], 1
0x18002cc5d  jmp     short loc_18002CCD7
0x18002cc5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc66  cmp     rcx, rbx
0x18002cc69  jz      loc_18002CCFD
0x18002cc6f  test    byte ptr [rcx+1Ch], 1
0x18002cc73  jz      short loc_18002CCDE
0x18002cc75  mov     edx, 43h ; 'C'
0x18002cc7a  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002cc81  mov     rcx, [rcx+10h]
0x18002cc85  call    WPP_SF_
0x18002cc8a  jmp     short loc_18002CCD7
0x18002cc8c  cmp     edi, 80070002h
0x18002cc92  jnz     short loc_18002CCAD
0x18002cc94  xor     edi, edi
0x18002cc96  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc9d  cmp     rcx, rbx
0x18002cca0  jz      short loc_18002CCFD
0x18002cca2  test    byte ptr [rcx+1Ch], 4
0x18002cca6  jz      short loc_18002CCDE
0x18002cca8  lea     edx, [rdi+44h]
0x18002ccab  jmp     short loc_18002CC7A
0x18002ccad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccb4  cmp     rcx, rbx
0x18002ccb7  jz      short loc_18002CCFD
0x18002ccb9  test    byte ptr [rcx+1Ch], 1
0x18002ccbd  jz      short loc_18002CCDE
0x18002ccbf  mov     edx, 45h ; 'E'
0x18002ccc4  mov     r9d, edi
0x18002ccc7  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002ccce  mov     rcx, [rcx+10h]
0x18002ccd2  call    WPP_SF_d
0x18002ccd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccde  cmp     rcx, rbx
0x18002cce1  jz      short loc_18002CCFD
0x18002cce3  test    byte ptr [rcx+1Ch], 8
0x18002cce7  jz      short loc_18002CCFD
0x18002cce9  mov     al, [r15]
0x18002ccec  mov     [rsp+70h+var_50], al
0x18002ccf0  mov     r9d, edi
0x18002ccf3  mov     rcx, [rcx+10h]
0x18002ccf7  call    WPP_SF_dc
0x18002ccfc  nop
0x18002ccfd  mov     rbx, [rbp+lpMem]
0x18002cd01  test    rbx, rbx
0x18002cd04  jz      short loc_18002CD1B
0x18002cd06  call    cs:__imp_GetProcessHeap
0x18002cd0c  mov     rcx, rax; hHeap
0x18002cd0f  mov     r8, rbx; lpMem
0x18002cd12  xor     edx, edx; dwFlags
0x18002cd14  call    cs:__imp_HeapFree
0x18002cd1a  nop
0x18002cd1b  mov     eax, edi
0x18002cd1d  mov     rcx, [rbp+var_8]
0x18002cd21  xor     rcx, rsp; StackCookie
0x18002cd24  call    __security_check_cookie
0x18002cd29  mov     rbx, [rsp+70h+arg_10]
0x18002cd31  add     rsp, 70h
0x18002cd35  pop     r15
0x18002cd37  pop     r14
0x18002cd39  pop     r13
0x18002cd3b  pop     r12
0x18002cd3d  pop     rdi
0x18002cd3e  pop     rsi
0x18002cd3f  pop     rbp
0x18002cd40  retn
```
