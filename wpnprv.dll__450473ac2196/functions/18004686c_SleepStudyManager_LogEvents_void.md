# SleepStudyManager::LogEvents(void)

- ea: `0x18004686c`
- end: `0x180046c21`
- name: `?LogEvents@SleepStudyManager@@QEAAJXZ`
- size: `949`
- prototype: `__int64 __fastcall(SleepStudyManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180046f50`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18004686c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180046931`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18004699c`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180046931`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18004699c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046a01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046a01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046bc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046bc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800469f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046bb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800469f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046bb4`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180046bab`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180046bab`

## string_xrefs

- `0x180046937`: `Data Connection Attempts`
- `0x1800469a2`: `Test Connection Attempts`

## pseudocode

```c
__int64 __fastcall SleepStudyManager::LogEvents(SleepStudyManager *this)
{
  unsigned int v2; // esi
  __int64 v3; // rbx
  __int64 v4; // rax
  ULONG v5; // r12d
  HANDLE ProcessHeap; // rax
  struct _EVENT_DATA_DESCRIPTOR *v7; // rax
  struct _EVENT_DATA_DESCRIPTOR *v8; // rbx
  unsigned int v9; // edi
  PVOID *v10; // rcx
  _QWORD *v11; // r15
  unsigned int v12; // r11d
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r10
  __int64 v19; // r9
  _WORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  HANDLE v23; // rax
  int v25; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v26; // [rsp+24h] [rbp-DCh] BYREF
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28[12]; // [rsp+34h] [rbp-CCh] BYREF
  _DWORD v29[2]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v30; // [rsp+48h] [rbp-B8h]
  _DWORD v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+70h] [rbp-90h]
  const wchar_t *v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h]
  _WORD *v37; // [rsp+88h] [rbp-78h]
  _WORD v38[264]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v39[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids);
  }
  v27 = 0;
  memset_0(v28, 0, 0x5Cu);
  memset_0(v38, 0, 0x208u);
  v2 = 2;
  LOBYTE(v25) = 0;
  v26 = 2;
  memset_0(v39, 0, 0x208u);
  _o__itow_s(*((unsigned int *)this + 9), v39, 260, 10);
  v27 = 3;
  v3 = -1;
  v30 = L"Data Connection Attempts";
  v4 = -1;
  v29[0] = 25;
  do
    ++v4;
  while ( v39[v4] );
  v31[0] = v4 + 1;
  v32 = v39;
  memset_0(v38, 0, 0x208u);
  _o__itow_s(*((unsigned int *)this + 10), v38, 260, 10);
  v33 = 3;
  v35 = L"Test Connection Attempts";
  v34 = 25;
  do
    ++v3;
  while ( v38[v3] );
  v36 = v3 + 1;
  v37 = v38;
  v5 = v26 + 4 * v26 + 3;
  ProcessHeap = GetProcessHeap();
  v7 = (struct _EVENT_DATA_DESCRIPTOR *)HeapAlloc(ProcessHeap, 8u, 16LL * v5);
  v8 = v7;
  if ( v7 )
  {
    v11 = (_QWORD *)((char *)this + 48);
    v9 = 0;
    v12 = 0;
    LOBYTE(v25) = *((_BYTE *)this + 48);
    v7->Ptr = (ULONGLONG)&v25;
    *(_QWORD *)&v7->Size = 1;
    v7[1].Ptr = (ULONGLONG)&v26;
    for ( *(_QWORD *)&v7[1].Size = 4; v12 < v26; *(&v8->Reserved + 2 * v21) = 0 )
    {
      v13 = 2LL * v2;
      v14 = v2 + 1;
      v15 = v2 + 2;
      v16 = v12;
      v14 *= 2;
      v17 = v15++;
      *((_QWORD *)&v8->Size + v13) = 16;
      ++v12;
      v18 = 12 * v16;
      v19 = v15;
      *(&v8->Ptr + v13) = (ULONGLONG)&v28[48 * v16 - 4];
      *((_QWORD *)&v8->Size + v14) = 4;
      *(&v8->Ptr + v14) = (ULONGLONG)&v29[12 * v16];
      LODWORD(v13) = v29[12 * v16];
      v8[v17].Ptr = *(_QWORD *)&v31[12 * v16 - 2];
      v8[v17].Size = 2 * v13;
      v8[v17].Reserved = 0;
      v8[v19].Ptr = (ULONGLONG)&v31[12 * v16];
      *(_QWORD *)&v8[v19].Size = 4;
      v20 = (&v32)[6 * v16];
      v21 = v15 + 1;
      v2 = v15 + 2;
      v21 *= 2;
      *(&v8->Size + 2 * v21) = 2 * v31[v18];
      *(&v8->Ptr + v21) = (ULONGLONG)v20;
    }
    v22 = v2;
    v8[v22].Ptr = (ULONGLONG)v11;
    *(_QWORD *)&v8[v22].Size = 8;
    EventWrite(*((_QWORD *)this + 3), &SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA, v5, v8);
    *v11 = 0;
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v8);
    goto LABEL_20;
  }
  v9 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids, 2147942414LL);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1E2,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\sleepstudymanager.cpp",
    (const char *)0x8007000ELL,
    v25);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    {
LABEL_21:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 6u )
        WPP_SF_(v10[2], 54, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids);
      return v9;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids, 2147942414LL);
LABEL_20:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  return v9;
}

```

## disassembly

```asm
0x18004686c  push    rbp
0x18004686e  push    rbx
0x18004686f  push    rsi
0x180046870  push    rdi
0x180046871  push    r12
0x180046873  push    r13
0x180046875  push    r14
0x180046877  push    r15
0x180046879  lea     rbp, [rsp-3C8h]
0x180046881  sub     rsp, 4C8h
0x180046888  mov     rax, cs:__security_cookie
0x18004688f  xor     rax, rsp
0x180046892  mov     [rbp+400h+var_50], rax
0x180046899  mov     r14, rcx
0x18004689c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468a3  lea     r15, WPP_GLOBAL_Control
0x1800468aa  cmp     rcx, r15
0x1800468ad  jz      short loc_1800468D0
0x1800468af  test    byte ptr [rcx+1Ch], 4
0x1800468b3  jz      short loc_1800468D0
0x1800468b5  cmp     byte ptr [rcx+19h], 6
0x1800468b9  jb      short loc_1800468D0
0x1800468bb  mov     rcx, [rcx+10h]
0x1800468bf  lea     r8, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids
0x1800468c6  mov     edx, 33h ; '3'
0x1800468cb  call    WPP_SF_
0x1800468d0  xor     r13d, r13d
0x1800468d3  lea     rcx, [rsp+500h+var_4CC]; void *
0x1800468d8  xor     edx, edx; Val
0x1800468da  mov     [rsp+500h+var_4D0], r13d
0x1800468df  lea     r8d, [r13+5Ch]; Size
0x1800468e3  call    memset_0
0x1800468e8  mov     edi, 208h
0x1800468ed  lea     rcx, [rbp+400h+var_470]; void *
0x1800468f1  mov     r8d, edi; Size
0x1800468f4  xor     edx, edx; Val
0x1800468f6  call    memset_0
0x1800468fb  lea     esi, [r13+2]
0x1800468ff  mov     byte ptr [rsp+500h+var_4E0], r13b; int
0x180046904  mov     r8d, edi; Size
0x180046907  mov     [rsp+500h+var_4DC], esi
0x18004690b  xor     edx, edx; Val
0x18004690d  lea     rcx, [rbp+400h+var_260]; void *
0x180046914  call    memset_0
0x180046919  mov     ecx, [r14+24h]
0x18004691d  lea     r12d, [r13+0Ah]
0x180046921  mov     r9d, r12d
0x180046924  lea     rdx, [rbp+400h+var_260]
0x18004692b  mov     r8d, 104h
0x180046931  call    cs:__imp__o__itow_s
0x180046937  lea     rax, aDataConnection; "Data Connection Attempts"
0x18004693e  mov     [rsp+500h+var_4D0], 3
0x180046946  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004694a  mov     [rsp+500h+var_4B8], rax
0x18004694f  mov     rax, rbx
0x180046952  mov     [rsp+500h+var_4C0], 19h
0x18004695a  lea     rcx, [rbp+400h+var_260]
0x180046961  inc     rax
0x180046964  cmp     [rcx+rax*2], r13w
0x180046969  jnz     short loc_180046961
0x18004696b  inc     eax
0x18004696d  lea     rcx, [rbp+400h+var_470]; void *
0x180046971  mov     [rsp+500h+var_4B0], eax
0x180046975  mov     r8, rdi; Size
0x180046978  lea     rax, [rbp+400h+var_260]
0x18004697f  xor     edx, edx; Val
0x180046981  mov     [rsp+500h+var_4A8], rax
0x180046986  call    memset_0
0x18004698b  mov     ecx, [r14+28h]
0x18004698f  lea     rdx, [rbp+400h+var_470]
0x180046993  mov     r9d, r12d
0x180046996  mov     r8d, 104h
0x18004699c  call    cs:__imp__o__itow_s
0x1800469a2  lea     rax, aTestConnection; "Test Connection Attempts"
0x1800469a9  mov     [rsp+500h+var_4A0], 3
0x1800469b1  mov     [rsp+500h+var_488], rax
0x1800469b6  lea     rax, [rbp+400h+var_470]
0x1800469ba  mov     [rsp+500h+var_490], 19h
0x1800469c2  inc     rbx
0x1800469c5  cmp     [rax+rbx*2], r13w
0x1800469ca  jnz     short loc_1800469C2
0x1800469cc  lea     eax, [rbx+1]
0x1800469cf  mov     [rbp+400h+var_480], eax
0x1800469d2  lea     rax, [rbp+400h+var_470]
0x1800469d6  mov     [rbp+400h+var_478], rax
0x1800469da  mov     eax, [rsp+500h+var_4DC]
0x1800469de  lea     r12d, ds:3[rax*4]
0x1800469e6  add     r12d, eax
0x1800469e9  mov     ebx, r12d
0x1800469ec  shl     rbx, 4
0x1800469f0  call    cs:__imp_GetProcessHeap
0x1800469f6  mov     r8, rbx; dwBytes
0x1800469f9  mov     edx, 8; dwFlags
0x1800469fe  mov     rcx, rax; hHeap
0x180046a01  call    cs:__imp_HeapAlloc
0x180046a07  mov     rbx, rax
0x180046a0a  test    rax, rax
0x180046a0d  jnz     loc_180046A9B
0x180046a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a1a  mov     edi, 8007000Eh
0x180046a1f  cmp     rcx, r15
0x180046a22  jz      short loc_180046A46
0x180046a24  test    byte ptr [rcx+1Ch], 4
0x180046a28  jz      short loc_180046A46
0x180046a2a  cmp     [rcx+19h], sil
0x180046a2e  jb      short loc_180046A46
0x180046a30  mov     rcx, [rcx+10h]
0x180046a34  lea     edx, [rax+34h]
0x180046a37  mov     r9d, edi
0x180046a3a  lea     r8, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids
0x180046a41  call    WPP_SF_d
0x180046a46  mov     rcx, [rbp+408h]; this
0x180046a4d  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180046a54  mov     r9d, edi; char *
0x180046a57  mov     edx, 1E2h; void *
0x180046a5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a68  cmp     rcx, r15
0x180046a6b  jz      loc_180046BFC
0x180046a71  test    byte ptr [rcx+1Ch], 80h
0x180046a75  jz      loc_180046BD6
0x180046a7b  mov     rcx, [rcx+10h]
0x180046a7f  lea     r8, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids
0x180046a86  mov     edx, 35h ; '5'
0x180046a8b  mov     r9d, 8007000Eh
0x180046a91  call    WPP_SF_d
0x180046a96  jmp     loc_180046BCF
0x180046a9b  lea     r15, [r14+30h]
0x180046a9f  mov     edi, r13d
0x180046aa2  mov     al, [r15]
0x180046aa5  mov     r11d, r13d
0x180046aa8  mov     byte ptr [rsp+500h+var_4E0], al
0x180046aac  lea     rax, [rsp+500h+var_4E0]
0x180046ab1  mov     [rbx], rax
0x180046ab4  lea     rax, [rsp+500h+var_4DC]
0x180046ab9  mov     qword ptr [rbx+8], 1
0x180046ac1  mov     [rbx+10h], rax
0x180046ac5  mov     qword ptr [rbx+18h], 4
0x180046acd  cmp     [rsp+500h+var_4DC], r13d
0x180046ad2  jbe     loc_180046B88
0x180046ad8  mov     ecx, esi
0x180046ada  inc     esi
0x180046adc  add     rcx, rcx
0x180046adf  mov     edx, esi
0x180046ae1  inc     esi
0x180046ae3  mov     eax, r11d
0x180046ae6  add     rdx, rdx
0x180046ae9  mov     r8d, esi
0x180046aec  add     r8, r8
0x180046aef  inc     esi
0x180046af1  mov     qword ptr [rbx+rcx*8+8], 10h
0x180046afa  inc     r11d
0x180046afd  lea     r10, [rax+rax*2]
0x180046b01  mov     r9d, esi
0x180046b04  shl     r10, 4
0x180046b08  lea     rax, [rsp+500h+var_4D0]
0x180046b0d  add     rax, r10
0x180046b10  add     r9, r9
0x180046b13  mov     [rbx+rcx*8], rax
0x180046b17  inc     esi
0x180046b19  mov     qword ptr [rbx+rdx*8+8], 4
0x180046b22  lea     rax, [rsp+500h+var_4C0]
0x180046b27  add     rax, r10
0x180046b2a  mov     [rbx+rdx*8], rax
0x180046b2e  mov     rax, [rsp+r10+500h+var_4B8]
0x180046b33  mov     ecx, [rsp+r10+500h+var_4C0]
0x180046b38  mov     [rbx+r8*8], rax
0x180046b3c  add     ecx, ecx
0x180046b3e  mov     [rbx+r8*8+8], ecx
0x180046b43  lea     rax, [rsp+500h+var_4B0]
0x180046b48  mov     [rbx+r8*8+0Ch], r13d
0x180046b4d  add     rax, r10
0x180046b50  mov     [rbx+r9*8], rax
0x180046b54  mov     qword ptr [rbx+r9*8+8], 4
0x180046b5d  mov     ecx, [rsp+r10+500h+var_4B0]
0x180046b62  mov     rax, [rsp+r10+500h+var_4A8]
0x180046b67  add     ecx, ecx
0x180046b69  mov     edx, esi
0x180046b6b  inc     esi
0x180046b6d  add     rdx, rdx
0x180046b70  mov     [rbx+rdx*8+8], ecx
0x180046b74  mov     [rbx+rdx*8], rax
0x180046b78  mov     [rbx+rdx*8+0Ch], r13d
0x180046b7d  cmp     r11d, [rsp+500h+var_4DC]
0x180046b82  jb      loc_180046AD8
0x180046b88  mov     eax, esi
0x180046b8a  lea     rdx, SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA; EventDescriptor
0x180046b91  add     rax, rax
0x180046b94  mov     r9, rbx; UserData
0x180046b97  mov     r8d, r12d; UserDataCount
0x180046b9a  mov     [rbx+rax*8], r15
0x180046b9e  mov     qword ptr [rbx+rax*8+8], 8
0x180046ba7  mov     rcx, [r14+18h]; RegHandle
0x180046bab  call    cs:__imp_EventWrite
0x180046bb1  mov     [r15], r13
0x180046bb4  call    cs:__imp_GetProcessHeap
0x180046bba  mov     r8, rbx; lpMem
0x180046bbd  xor     edx, edx; dwFlags
0x180046bbf  mov     rcx, rax; hHeap
0x180046bc2  call    cs:__imp_HeapFree
0x180046bc8  lea     r15, WPP_GLOBAL_Control
0x180046bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bd6  cmp     rcx, r15
0x180046bd9  jz      short loc_180046BFC
0x180046bdb  test    byte ptr [rcx+1Ch], 4
0x180046bdf  jz      short loc_180046BFC
0x180046be1  cmp     byte ptr [rcx+19h], 6
0x180046be5  jb      short loc_180046BFC
0x180046be7  mov     rcx, [rcx+10h]
0x180046beb  lea     r8, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids
0x180046bf2  mov     edx, 36h ; '6'
0x180046bf7  call    WPP_SF_
0x180046bfc  mov     eax, edi
0x180046bfe  mov     rcx, [rbp+400h+var_50]
0x180046c05  xor     rcx, rsp; StackCookie
0x180046c08  call    __security_check_cookie
0x180046c0d  add     rsp, 4C8h
0x180046c14  pop     r15
0x180046c16  pop     r14
0x180046c18  pop     r13
0x180046c1a  pop     r12
0x180046c1c  pop     rdi
0x180046c1d  pop     rsi
0x180046c1e  pop     rbx
0x180046c1f  pop     rbp
0x180046c20  retn
```
