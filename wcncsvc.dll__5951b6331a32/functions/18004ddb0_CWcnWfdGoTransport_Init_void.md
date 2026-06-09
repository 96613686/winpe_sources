# CWcnWfdGoTransport::Init(void)

- ea: `0x18004ddb0`
- end: `0x18004e03f`
- name: `?Init@CWcnWfdGoTransport@@UEAAJXZ`
- size: `655`
- prototype: `__int64 __fastcall(CWcnWfdGoTransport *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18001e828`
- `0x18001f10c`
- `0x18004ddb0`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004de14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004de14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004de3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004de3f`
- `wlanapi!WFDOpenHandleInt` at `0x18004de29`
- `wlanapi!WFDOpenHandleInt` at `0x18004de29`

## pseudocode

```c
__int64 __fastcall CWcnWfdGoTransport::Init(CWcnWfdGoTransport *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  bool v5; // sf
  _QWORD *v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r10
  int v13; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 10, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, Indent);
  }
  v13 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v4 = WFDOpenHandleInt(1, &v13, (char *)this + 256);
  if ( !v4 )
    *((_DWORD *)this + 62) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v5 = (v4 & 0x80000000) != 0;
  if ( (int)v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = (v4 & 0x80000000) != 0;
  }
  if ( !v5 )
  {
    v9 = CWcnMessage::Init((__int64)this + 24, 8, (__int64)qword_180069110, 8);
    v4 = v9;
    if ( v9 >= 0 )
    {
      v9 = CWcnMessage::SetWfaVendorExtensionSubMessage(
             (CWcnWfdGoTransport *)((char *)this + 24),
             (const struct tagWCN_MESSAGE_RULE *)qword_180069058,
             2u);
      v4 = v9;
      if ( v9 >= 0 )
      {
        v9 = CWcnMessage::Init((__int64)this + 80, 8, (__int64)qword_180069080, 17);
        v4 = v9;
        if ( v9 >= 0 )
        {
          v9 = CWcnMessage::SetWfaVendorExtensionSubMessage(
                 (CWcnWfdGoTransport *)((char *)this + 80),
                 (const struct tagWCN_MESSAGE_RULE *)qword_180069068,
                 2u);
          v4 = v9;
          if ( v9 >= 0 )
          {
            v9 = CWcnMessage::Init((__int64)this + 136, 8, (__int64)qword_180069160, 16);
            v4 = v9;
            if ( v9 >= 0 )
            {
              if ( *((_DWORD *)this + 2) < 7u )
                *(_QWORD *)(*((_QWORD *)g_pWcnService + 7) + 8LL * *((unsigned int *)this + 2) + 448) = ((unsigned __int64)this + 16) & -(__int64)(this != 0);
              goto LABEL_36;
            }
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v4;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_37;
            v7 = 16;
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v4;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_37;
            v7 = 15;
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v4;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_37;
          v7 = 14;
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v4;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_37;
        v7 = 13;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_37;
      v7 = 12;
    }
    v8 = (unsigned int)v9;
LABEL_12:
    WPP_SF_d(v6[2], v7, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v8);
LABEL_36:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 11;
    v8 = v4;
    goto LABEL_12;
  }
LABEL_37:
  if ( v6 != &WPP_GLOBAL_Control && ((v4 & 0x80000000) != 0 || *((_BYTE *)v6 + 25) >= 6u) )
  {
    v10 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v11 + 16), 17, (unsigned int)WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v10, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18004ddb0  push    rbx
0x18004ddb2  push    rbp
0x18004ddb3  push    rsi
0x18004ddb4  push    rdi
0x18004ddb5  push    r14
0x18004ddb7  push    r15
0x18004ddb9  sub     rsp, 38h
0x18004ddbd  mov     rdi, rcx
0x18004ddc0  mov     r10, cs:WPP_GLOBAL_Control
0x18004ddc7  lea     rbp, WPP_GLOBAL_Control
0x18004ddce  lea     r15, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ddd5  mov     r14d, 1
0x18004dddb  cmp     r10, rbp
0x18004ddde  jz      short loc_18004DE02
0x18004dde0  cmp     byte ptr [r10+19h], 6
0x18004dde5  jb      short loc_18004DE02
0x18004dde7  mov     ecx, r14d; int
0x18004ddea  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004ddef  mov     rcx, [r10+10h]
0x18004ddf3  lea     edx, [r14+9]
0x18004ddf7  mov     r9, rax
0x18004ddfa  mov     r8, r15
0x18004ddfd  call    WPP_SF_s
0x18004de02  lea     rsi, [rdi+0D0h]
0x18004de09  mov     [rsp+68h+arg_0], 0
0x18004de11  mov     rcx, rsi; lpCriticalSection
0x18004de14  call    cs:__imp_EnterCriticalSection
0x18004de1a  lea     r8, [rdi+100h]
0x18004de21  mov     ecx, r14d
0x18004de24  lea     rdx, [rsp+68h+arg_0]
0x18004de29  call    cs:__imp_WFDOpenHandleInt
0x18004de2f  mov     ebx, eax
0x18004de31  test    eax, eax
0x18004de33  jnz     short loc_18004DE3C
0x18004de35  mov     [rdi+0F8h], r14d
0x18004de3c  mov     rcx, rsi; lpCriticalSection
0x18004de3f  call    cs:__imp_LeaveCriticalSection
0x18004de45  test    ebx, ebx
0x18004de47  jle     short loc_18004DE54
0x18004de49  movzx   ebx, bx
0x18004de4c  or      ebx, 80070000h
0x18004de52  test    ebx, ebx
0x18004de54  jns     short loc_18004DE8A
0x18004de56  mov     r10, cs:WPP_GLOBAL_Control
0x18004de5d  cmp     r10, rbp
0x18004de60  jz      loc_18004E030
0x18004de66  cmp     byte ptr [r10+19h], 2
0x18004de6b  jb      loc_18004E000
0x18004de71  mov     edx, 0Bh
0x18004de76  mov     r9d, ebx
0x18004de79  mov     rcx, [r10+10h]
0x18004de7d  mov     r8, r15
0x18004de80  call    WPP_SF_d
0x18004de85  jmp     loc_18004DFF9
0x18004de8a  mov     r14d, 8
0x18004de90  lea     r8, qword_180069110
0x18004de97  mov     r9d, r14d
0x18004de9a  lea     rcx, [rdi+18h]
0x18004de9e  mov     edx, r14d
0x18004dea1  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x18004dea6  mov     ebx, eax
0x18004dea8  test    eax, eax
0x18004deaa  jns     short loc_18004DED0
0x18004deac  mov     r10, cs:WPP_GLOBAL_Control
0x18004deb3  cmp     r10, rbp
0x18004deb6  jz      loc_18004E030
0x18004debc  cmp     byte ptr [r10+19h], 2
0x18004dec1  jb      loc_18004E000
0x18004dec7  lea     edx, [r14+4]
0x18004decb  mov     r9d, eax
0x18004dece  jmp     short loc_18004DE79
0x18004ded0  mov     r8d, 2; unsigned __int64
0x18004ded6  lea     rdx, qword_180069058; struct tagWCN_MESSAGE_RULE *
0x18004dedd  lea     rcx, [rdi+18h]; this
0x18004dee1  call    ?SetWfaVendorExtensionSubMessage@CWcnMessage@@QEAAJPEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::SetWfaVendorExtensionSubMessage(tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x18004dee6  mov     ebx, eax
0x18004dee8  test    eax, eax
0x18004deea  jns     short loc_18004DF0E
0x18004deec  mov     r10, cs:WPP_GLOBAL_Control
0x18004def3  cmp     r10, rbp
0x18004def6  jz      loc_18004E030
0x18004defc  cmp     byte ptr [r10+19h], 2
0x18004df01  jb      loc_18004E000
0x18004df07  mov     edx, 0Dh
0x18004df0c  jmp     short loc_18004DECB
0x18004df0e  mov     r9d, 11h
0x18004df14  lea     r8, qword_180069080
0x18004df1b  mov     edx, r14d
0x18004df1e  lea     rcx, [rdi+50h]
0x18004df22  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x18004df27  mov     ebx, eax
0x18004df29  test    eax, eax
0x18004df2b  jns     short loc_18004DF52
0x18004df2d  mov     r10, cs:WPP_GLOBAL_Control
0x18004df34  cmp     r10, rbp
0x18004df37  jz      loc_18004E030
0x18004df3d  cmp     byte ptr [r10+19h], 2
0x18004df42  jb      loc_18004E000
0x18004df48  mov     edx, 0Eh
0x18004df4d  jmp     loc_18004DECB
0x18004df52  mov     r8d, 2; unsigned __int64
0x18004df58  lea     rdx, qword_180069068; struct tagWCN_MESSAGE_RULE *
0x18004df5f  lea     rcx, [rdi+50h]; this
0x18004df63  call    ?SetWfaVendorExtensionSubMessage@CWcnMessage@@QEAAJPEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::SetWfaVendorExtensionSubMessage(tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x18004df68  mov     ebx, eax
0x18004df6a  test    eax, eax
0x18004df6c  jns     short loc_18004DF8F
0x18004df6e  mov     r10, cs:WPP_GLOBAL_Control
0x18004df75  cmp     r10, rbp
0x18004df78  jz      loc_18004E030
0x18004df7e  cmp     byte ptr [r10+19h], 2
0x18004df83  jb      short loc_18004E000
0x18004df85  mov     edx, 0Fh
0x18004df8a  jmp     loc_18004DECB
0x18004df8f  mov     esi, 10h
0x18004df94  lea     rcx, [rdi+88h]
0x18004df9b  mov     r9d, esi
0x18004df9e  lea     r8, qword_180069160
0x18004dfa5  mov     edx, r14d
0x18004dfa8  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x18004dfad  mov     ebx, eax
0x18004dfaf  test    eax, eax
0x18004dfb1  jns     short loc_18004DFCD
0x18004dfb3  mov     r10, cs:WPP_GLOBAL_Control
0x18004dfba  cmp     r10, rbp
0x18004dfbd  jz      short loc_18004E030
0x18004dfbf  cmp     byte ptr [r10+19h], 2
0x18004dfc4  jb      short loc_18004E000
0x18004dfc6  mov     edx, esi
0x18004dfc8  jmp     loc_18004DECB
0x18004dfcd  mov     rax, rdi
0x18004dfd0  lea     rcx, [rdi+10h]
0x18004dfd4  neg     rax
0x18004dfd7  sbb     r8, r8
0x18004dfda  and     r8, rcx
0x18004dfdd  cmp     dword ptr [rdi+8], 7
0x18004dfe1  jnb     short loc_18004DFF9
0x18004dfe3  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18004dfea  mov     edx, [rdi+8]
0x18004dfed  mov     rcx, [rax+38h]
0x18004dff1  mov     [rcx+rdx*8+1C0h], r8
0x18004dff9  mov     r10, cs:WPP_GLOBAL_Control
0x18004e000  cmp     r10, rbp
0x18004e003  jz      short loc_18004E030
0x18004e005  test    ebx, ebx
0x18004e007  js      short loc_18004E010
0x18004e009  cmp     byte ptr [r10+19h], 6
0x18004e00e  jb      short loc_18004E030
0x18004e010  or      ecx, 0FFFFFFFFh; int
0x18004e013  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004e018  mov     rcx, [r10+10h]
0x18004e01c  mov     edx, 11h
0x18004e021  mov     r9, rax
0x18004e024  mov     [rsp+68h+var_48], ebx
0x18004e028  mov     r8, r15
0x18004e02b  call    WPP_SF_sd
0x18004e030  mov     eax, ebx
0x18004e032  add     rsp, 38h
0x18004e036  pop     r15
0x18004e038  pop     r14
0x18004e03a  pop     rdi
0x18004e03b  pop     rsi
0x18004e03c  pop     rbp
0x18004e03d  pop     rbx
0x18004e03e  retn
```
