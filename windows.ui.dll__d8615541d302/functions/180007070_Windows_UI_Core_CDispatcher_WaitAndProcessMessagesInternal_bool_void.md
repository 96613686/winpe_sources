# Windows::UI::Core::CDispatcher::WaitAndProcessMessagesInternal(bool,void *)

- ea: `0x180007070`
- end: `0x180007371`
- name: `?WaitAndProcessMessagesInternal@CDispatcher@Core@UI@Windows@@AEAA_N_NPEAX@Z`
- size: `769`
- prototype: `bool(Windows::UI::Core::CDispatcher *__hidden this, bool, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800062d0`
- `0x180006d90`

## callees

- `0x180007070`
- `0x180007380`
- `0x180056d3c`
- `0x180071c60`
- `0x18008aaf0`
- `0x1800c7366`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800071db`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800071db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000720c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800072e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000720c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800072e2`
- `combase!__imp_CoBeginProcessEvents` at `0x1800070ef`
- `combase!__imp_CoBeginProcessEvents` at `0x1800070ef`
- `combase!__imp_CoMsgWaitInProcessEvents` at `0x180007168`
- `combase!__imp_CoMsgWaitInProcessEvents` at `0x180007168`
- `combase!__imp_CoEndProcessEvents` at `0x18000718a`
- `combase!__imp_CoEndProcessEvents` at `0x18000718a`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CDispatcher::WaitAndProcessMessagesInternal(
        Windows::UI::Core::CDispatcher *this,
        __int64 a2,
        void *a3)
{
  int v3; // r15d
  char v5; // bl
  unsigned __int8 v7; // r13
  unsigned int v8; // r14d
  __int64 v9; // r12
  PVOID *v10; // rcx
  char v11; // al
  int v12; // eax
  void *v14; // rcx
  DWORD v15; // edi
  __int64 v16; // [rsp+28h] [rbp-E0h]
  bool v17; // [rsp+40h] [rbp-C8h] BYREF
  bool v18; // [rsp+41h] [rbp-C7h] BYREF
  __int64 v19; // [rsp+48h] [rbp-C0h] BYREF
  void *v20; // [rsp+50h] [rbp-B8h]
  _BYTE v21[96]; // [rsp+60h] [rbp-A8h] BYREF

  v20 = 0;
  v3 = 0;
  v19 = *((_QWORD *)this + 97);
  v5 = a2;
  v7 = 1;
  v8 = 1;
  if ( a3 )
  {
    v20 = a3;
    v8 = 2;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qDdq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, this, *((_DWORD *)this + 30));
    }
  }
  v9 = *((_QWORD *)this + 20);
  memset_0(v21, 0, sizeof(v21));
  CoBeginProcessEvents(v21);
  while ( 1 )
  {
    v17 = 0;
    v18 = 0;
    if ( Windows::UI::Core::CDispatcher::ProcessMessage(this, 1, &v17, &v18) )
    {
      v7 = 0;
      goto LABEL_11;
    }
    if ( v17 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_6;
    }
    if ( v18 )
      goto LABEL_15;
    v14 = (void *)*((_QWORD *)this + 27);
    if ( !v14 )
    {
      SleepEx(0, 1);
LABEL_15:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    WaitForSingleObjectEx(v14, 1u, 1);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
        this,
        *((_DWORD *)this + 30));
      goto LABEL_15;
    }
LABEL_16:
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_7;
    }
LABEL_6:
    v11 = 1;
LABEL_7:
    if ( !v5 || !v11 )
    {
      v12 = CoMsgWaitInProcessEvents(v21, v8, &v19, 0xFFFFFFFFLL, 7423, 6);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v3 = v12;
    }
    if ( a3 )
    {
      if ( v3 == v8 - 1 )
        break;
      v15 = WaitForSingleObjectEx(a3, 0, 1);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        LODWORD(v16) = v15;
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
          this,
          *((_DWORD *)this + 30),
          v16);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v15 )
        break;
    }
    if ( v5 )
      goto LABEL_11;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 4u )
  {
    LODWORD(v16) = v3;
    WPP_SF_qDD(v10[2], 40, &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids, this, *((_DWORD *)this + 30), v16);
  }
LABEL_11:
  CoEndProcessEvents(v21);
  return v7;
}

```

## disassembly

```asm
0x180007070  mov     [rsp+arg_8], rbx
0x180007075  push    rbp
0x180007076  push    rsi
0x180007077  push    rdi
0x180007078  push    r12
0x18000707a  push    r13
0x18000707c  push    r14
0x18000707e  push    r15
0x180007080  sub     rsp, 0D0h
0x180007087  mov     rax, cs:__security_cookie
0x18000708e  xor     rax, rsp
0x180007091  mov     [rsp+108h+var_48], rax
0x180007099  xor     eax, eax
0x18000709b  lea     rdi, WPP_GLOBAL_Control
0x1800070a2  mov     [rsp+108h+var_B8], rax
0x1800070a7  xor     r15d, r15d
0x1800070aa  mov     rax, [rcx+308h]
0x1800070b1  mov     rsi, r8
0x1800070b4  mov     [rsp+108h+var_C0], rax
0x1800070b9  movzx   ebx, dl
0x1800070bc  mov     rbp, rcx
0x1800070bf  mov     r13b, 1
0x1800070c2  mov     r14d, 1
0x1800070c8  test    r8, r8
0x1800070cb  jnz     loc_180007286
0x1800070d1  mov     r12, [rbp+0A0h]
0x1800070d8  lea     rcx, [rsp+108h+var_A8]; void *
0x1800070dd  xor     edx, edx; Val
0x1800070df  mov     r8d, 60h ; '`'; Size
0x1800070e5  call    memset_0
0x1800070ea  lea     rcx, [rsp+108h+var_A8]
0x1800070ef  call    cs:__imp_CoBeginProcessEvents
0x1800070f5  nop     word ptr [rax+rax+00000000h]
0x180007100  lea     r9, [rsp+108h+var_C7]; bool *
0x180007105  mov     [rsp+108h+var_C8], 0
0x18000710a  lea     r8, [rsp+108h+var_C8]; bool *
0x18000710f  mov     [rsp+108h+var_C7], 0
0x180007114  movzx   edx, r13b; bool
0x180007118  mov     rcx, rbp; this
0x18000711b  call    ?ProcessMessage@CDispatcher@Core@UI@Windows@@AEAA_N_NPEA_N1@Z; Windows::UI::Core::CDispatcher::ProcessMessage(bool,bool *,bool *)
0x180007120  test    al, al
0x180007122  jnz     loc_180007369
0x180007128  cmp     [rsp+108h+var_C8], al
0x18000712c  jz      loc_1800071BF
0x180007132  mov     rcx, cs:WPP_GLOBAL_Control
0x180007139  movzx   eax, r13b
0x18000713d  test    bl, bl
0x18000713f  jnz     loc_1800072D2
0x180007145  mov     dword ptr [rsp+108h+var_E0], 6
0x18000714d  lea     r8, [rsp+108h+var_C0]
0x180007152  mov     r9d, 0FFFFFFFFh
0x180007158  mov     [rsp+108h+var_E8], 1CFFh
0x180007160  mov     edx, r14d
0x180007163  lea     rcx, [rsp+108h+var_A8]
0x180007168  call    cs:__imp_CoMsgWaitInProcessEvents
0x18000716e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007175  mov     r15d, eax
0x180007178  test    rsi, rsi
0x18000717b  jnz     short loc_1800071F8
0x18000717d  test    bl, bl
0x18000717f  jz      loc_180007100
0x180007185  lea     rcx, [rsp+108h+var_A8]
0x18000718a  call    cs:__imp_CoEndProcessEvents
0x180007190  movzx   eax, r13b
0x180007194  mov     rcx, [rsp+108h+var_48]
0x18000719c  xor     rcx, rsp; StackCookie
0x18000719f  call    __security_check_cookie
0x1800071a4  mov     rbx, [rsp+108h+arg_8]
0x1800071ac  add     rsp, 0D0h
0x1800071b3  pop     r15
0x1800071b5  pop     r14
0x1800071b7  pop     r13
0x1800071b9  pop     r12
0x1800071bb  pop     rdi
0x1800071bc  pop     rsi
0x1800071bd  pop     rbp
0x1800071be  retn
0x1800071bf  cmp     [rsp+108h+var_C7], 0
0x1800071c4  jnz     short loc_1800071E1
0x1800071c6  mov     rcx, [rbp+0D8h]; hHandle
0x1800071cd  mov     edx, 1; dwMilliseconds
0x1800071d2  test    rcx, rcx
0x1800071d5  jnz     loc_1800072DF
0x1800071db  call    cs:__imp_SleepEx
0x1800071e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071e8  test    r12, r12
0x1800071eb  jnz     loc_180007139
0x1800071f1  xor     al, al
0x1800071f3  jmp     loc_18000713D
0x1800071f8  lea     eax, [r14-1]
0x1800071fc  cmp     r15d, eax
0x1800071ff  jz      short loc_180007240
0x180007201  xor     edx, edx; dwMilliseconds
0x180007203  mov     r8d, 1; bAlertable
0x180007209  mov     rcx, rsi; hHandle
0x18000720c  call    cs:__imp_WaitForSingleObjectEx
0x180007212  mov     edi, eax
0x180007214  mov     rcx, cs:WPP_GLOBAL_Control
0x18000721b  lea     rax, WPP_GLOBAL_Control
0x180007222  cmp     rcx, rax
0x180007225  jz      short loc_180007231
0x180007227  test    byte ptr [rcx+1Ch], 4
0x18000722b  jnz     loc_180007330
0x180007231  test    edi, edi
0x180007233  lea     rdi, WPP_GLOBAL_Control
0x18000723a  jnz     loc_18000717D
0x180007240  cmp     rcx, rdi
0x180007243  jz      loc_180007185
0x180007249  test    byte ptr [rcx+1Ch], 4
0x18000724d  jz      loc_180007185
0x180007253  cmp     byte ptr [rcx+19h], 4
0x180007257  jb      loc_180007185
0x18000725d  mov     eax, [rbp+78h]
0x180007260  lea     r8, WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids
0x180007267  mov     rcx, [rcx+10h]
0x18000726b  mov     edx, 28h ; '('
0x180007270  mov     dword ptr [rsp+108h+var_E0], r15d
0x180007275  mov     r9, rbp
0x180007278  mov     [rsp+108h+var_E8], eax
0x18000727c  call    WPP_SF_qDD
0x180007281  jmp     loc_180007185
0x180007286  mov     [rsp+108h+var_B8], rsi
0x18000728b  mov     r14d, 2
0x180007291  mov     rcx, cs:WPP_GLOBAL_Control
0x180007298  cmp     rcx, rdi
0x18000729b  jz      loc_1800070D1
0x1800072a1  test    byte ptr [rcx+1Ch], 4
0x1800072a5  jz      loc_1800070D1
0x1800072ab  cmp     byte ptr [rcx+19h], 4
0x1800072af  jb      loc_1800070D1
0x1800072b5  mov     eax, [rbp+78h]
0x1800072b8  mov     r9, rbp
0x1800072bb  mov     rcx, [rcx+10h]
0x1800072bf  mov     [rsp+108h+var_D8], rsi
0x1800072c4  mov     [rsp+108h+var_E8], eax
0x1800072c8  call    WPP_SF_qDdq
0x1800072cd  jmp     loc_1800070D1
0x1800072d2  test    al, al
0x1800072d4  jz      loc_180007145
0x1800072da  jmp     loc_180007178
0x1800072df  mov     r8d, edx; bAlertable
0x1800072e2  call    cs:__imp_WaitForSingleObjectEx
0x1800072e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072ef  cmp     rcx, rdi
0x1800072f2  jz      loc_1800071E8
0x1800072f8  test    byte ptr [rcx+1Ch], 4
0x1800072fc  jz      loc_1800071E8
0x180007302  cmp     byte ptr [rcx+19h], 4
0x180007306  jb      loc_1800071E8
0x18000730c  mov     eax, [rbp+78h]
0x18000730f  lea     r8, WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids
0x180007316  mov     rcx, [rcx+10h]
0x18000731a  mov     edx, 27h ; '''
0x18000731f  mov     r9, rbp
0x180007322  mov     [rsp+108h+var_E8], eax
0x180007326  call    WPP_SF_qD
0x18000732b  jmp     loc_1800071E1
0x180007330  cmp     byte ptr [rcx+19h], 4
0x180007334  jb      loc_180007231
0x18000733a  mov     eax, [rbp+78h]
0x18000733d  lea     r8, WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids
0x180007344  mov     rcx, [rcx+10h]
0x180007348  mov     edx, 0Dh
0x18000734d  mov     dword ptr [rsp+108h+var_E0], edi
0x180007351  mov     r9, rbp
0x180007354  mov     [rsp+108h+var_E8], eax
0x180007358  call    WPP_SF_qDD
0x18000735d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007364  jmp     loc_180007231
0x180007369  xor     r13b, r13b
0x18000736c  jmp     loc_180007185
```
