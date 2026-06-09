# SessionConfig::BuildTracePropsFromChannelRegistryConfig_Impl(_EVENT_TRACE_PROPERTIES *)

- ea: `0x14002dc00`
- end: `0x14002dda9`
- name: `?BuildTracePropsFromChannelRegistryConfig_Impl@SessionConfig@@AEBAXPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `425`
- prototype: `void(SessionConfig *__hidden this, struct _EVENT_TRACE_PROPERTIES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013658`

## callees

- `0x14001b580`
- `0x14001b5b4`
- `0x140022510`
- `0x14002dc00`
- `0x14003181c`

## pseudocode

```c
void __fastcall SessionConfig::BuildTracePropsFromChannelRegistryConfig_Impl(
        SessionConfig *this,
        struct _EVENT_TRACE_PROPERTIES *a2)
{
  __int64 v2; // rsi
  __int64 v5; // r15
  char v6; // r12
  __int64 v7; // r14
  ULONG v8; // eax
  ULONG v9; // eax
  ULONG v10; // eax
  ULONG v11; // eax
  ULONG v12; // edx
  __int64 v13; // rax
  int v14; // ebx
  int v15; // eax
  ULONG v16; // ecx
  __int128 Buf1; // [rsp+20h] [rbp-18h] BYREF

  v2 = *(_QWORD *)this;
  v5 = *(_QWORD *)(*(_QWORD *)this + 200LL);
  v6 = *(_BYTE *)(*(_QWORD *)this + 249LL);
  v7 = (*(_QWORD *)(*(_QWORD *)this + 208LL) - v5) >> 1;
  memset_0(a2, 0, sizeof(struct _EVENT_TRACE_PROPERTIES));
  a2->Wnode.BufferSize = 120;
  a2->Wnode.Flags = 0x20000;
  a2->Wnode.Guid = *(GUID *)((char *)this + 72);
  if ( !*(_BYTE *)(v2 + 48) || (v8 = 1, *(_BYTE *)(v2 + 48) != 1) )
    v8 = 2;
  a2->Wnode.ClientContext = v8;
  *(_QWORD *)&a2->BufferSize = 64;
  a2->MaximumBuffers = 64;
  if ( (unsigned __int8)(v6 - 2) > 1u )
  {
    *(_QWORD *)&Buf1 = v5;
    *((_QWORD *)&Buf1 + 1) = v7;
    if ( (unsigned __int8)IsSystemChannel(&Buf1)
      || (*(_QWORD *)&Buf1 = v5, *((_QWORD *)&Buf1 + 1) = v7, IsSecurityChannel(&Buf1)) )
    {
      a2->MaximumBuffers = 16;
    }
  }
  v9 = *(_DWORD *)(v2 + 24);
  if ( v9 )
    a2->BufferSize = v9;
  v10 = *(_DWORD *)(v2 + 28);
  if ( v10 )
    a2->MinimumBuffers = v10;
  v11 = *(_DWORD *)(v2 + 32);
  if ( v11 )
    a2->MaximumBuffers = v11;
  v12 = *(_DWORD *)(v2 + 36) / 0x3E8u;
  if ( !v12 )
    v12 = 1;
  a2->FlushTimer = v12;
  if ( (unsigned __int8)(v6 - 2) > 1u )
    goto LABEL_21;
  v13 = *(_QWORD *)(v2 + 152) >> 20;
  if ( !(_DWORD)v13 )
    LODWORD(v13) = 2;
  a2->MaximumFileSize = v13;
  if ( (unsigned __int8)(v6 - 2) > 1u )
  {
LABEL_21:
    *(_QWORD *)&Buf1 = v5;
    *((_QWORD *)&Buf1 + 1) = v7;
    if ( (unsigned __int8)IsSystemChannel(&Buf1) )
    {
      v14 = -1744830208;
    }
    else
    {
      *(_QWORD *)&Buf1 = v5;
      v14 = 402653440;
      *((_QWORD *)&Buf1 + 1) = v7;
      if ( !IsSecurityChannel(&Buf1) )
        v14 = 419430656;
    }
  }
  else
  {
    v14 = 134217730 - (*(_BYTE *)(v2 + 160) != 0);
  }
  Buf1 = *(_OWORD *)(v2 + 8);
  v15 = memcmp_0(&Buf1, &GUID_NULL, 0x10u);
  v16 = v14 | 0x80;
  if ( v15 )
    v16 = v14;
  a2->LogFileMode = v16;
}

```

## disassembly

```asm
0x14002dc00  push    rbp
0x14002dc02  push    rbx
0x14002dc03  push    rsi
0x14002dc04  push    rdi
0x14002dc05  push    r12
0x14002dc07  push    r13
0x14002dc09  push    r14
0x14002dc0b  push    r15
0x14002dc0d  mov     rbp, rsp
0x14002dc10  sub     rsp, 38h
0x14002dc14  mov     rsi, [rcx]
0x14002dc17  mov     rdi, rdx
0x14002dc1a  mov     rbx, rcx
0x14002dc1d  mov     r13d, 78h ; 'x'
0x14002dc23  mov     r8d, r13d; Size
0x14002dc26  xor     edx, edx; Val
0x14002dc28  mov     rcx, rdi; void *
0x14002dc2b  mov     r15, [rsi+0C8h]
0x14002dc32  mov     r14, [rsi+0D0h]
0x14002dc39  mov     r12b, [rsi+0F9h]
0x14002dc40  sub     r14, r15
0x14002dc43  sar     r14, 1
0x14002dc46  call    memset_0
0x14002dc4b  mov     [rdi], r13d
0x14002dc4e  mov     dword ptr [rdi+2Ch], 20000h
0x14002dc55  movups  xmm0, xmmword ptr [rbx+48h]
0x14002dc59  lea     ebx, [r13-76h]
0x14002dc5d  lea     r13d, [rbx-1]
0x14002dc61  movdqu  xmmword ptr [rdi+18h], xmm0
0x14002dc66  movzx   ecx, byte ptr [rsi+30h]
0x14002dc6a  test    ecx, ecx
0x14002dc6c  jz      short loc_14002DC76
0x14002dc6e  mov     eax, r13d
0x14002dc71  cmp     ecx, r13d
0x14002dc74  jz      short loc_14002DC78
0x14002dc76  mov     eax, ebx
0x14002dc78  mov     [rdi+28h], eax
0x14002dc7b  mov     eax, 40h ; '@'
0x14002dc80  mov     [rdi+30h], rax
0x14002dc84  mov     [rdi+38h], eax
0x14002dc87  mov     al, r12b
0x14002dc8a  sub     al, bl
0x14002dc8c  cmp     al, r13b
0x14002dc8f  jbe     short loc_14002DCC2
0x14002dc91  lea     rcx, [rbp+Buf1]
0x14002dc95  mov     qword ptr [rbp+Buf1], r15
0x14002dc99  mov     qword ptr [rbp+Buf1+8], r14
0x14002dc9d  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002dca2  test    al, al
0x14002dca4  jnz     short loc_14002DCBB
0x14002dca6  lea     rcx, [rbp+Buf1]
0x14002dcaa  mov     qword ptr [rbp+Buf1], r15
0x14002dcae  mov     qword ptr [rbp+Buf1+8], r14
0x14002dcb2  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002dcb7  test    al, al
0x14002dcb9  jz      short loc_14002DCC2
0x14002dcbb  mov     dword ptr [rdi+38h], 10h
0x14002dcc2  mov     eax, [rsi+18h]
0x14002dcc5  test    eax, eax
0x14002dcc7  jz      short loc_14002DCCC
0x14002dcc9  mov     [rdi+30h], eax
0x14002dccc  mov     eax, [rsi+1Ch]
0x14002dccf  test    eax, eax
0x14002dcd1  jz      short loc_14002DCD6
0x14002dcd3  mov     [rdi+34h], eax
0x14002dcd6  mov     eax, [rsi+20h]
0x14002dcd9  test    eax, eax
0x14002dcdb  jz      short loc_14002DCE0
0x14002dcdd  mov     [rdi+38h], eax
0x14002dce0  mov     eax, 10624DD3h
0x14002dce5  mul     dword ptr [rsi+24h]
0x14002dce8  mov     al, r12b
0x14002dceb  shr     edx, 6
0x14002dcee  test    edx, edx
0x14002dcf0  cmovz   edx, r13d
0x14002dcf4  sub     al, bl
0x14002dcf6  mov     [rdi+44h], edx
0x14002dcf9  cmp     al, r13b
0x14002dcfc  ja      short loc_14002DD2B
0x14002dcfe  mov     rax, [rsi+98h]
0x14002dd05  shr     rax, 14h
0x14002dd09  test    eax, eax
0x14002dd0b  cmovz   eax, ebx
0x14002dd0e  sub     r12b, bl
0x14002dd11  mov     [rdi+3Ch], eax
0x14002dd14  cmp     r12b, r13b
0x14002dd17  ja      short loc_14002DD2B
0x14002dd19  mov     al, [rsi+0A0h]
0x14002dd1f  neg     al
0x14002dd21  sbb     ebx, ebx
0x14002dd23  add     ebx, 8000002h
0x14002dd29  jmp     short loc_14002DD66
0x14002dd2b  lea     rcx, [rbp+Buf1]
0x14002dd2f  mov     qword ptr [rbp+Buf1], r15
0x14002dd33  mov     qword ptr [rbp+Buf1+8], r14
0x14002dd37  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002dd3c  test    al, al
0x14002dd3e  jz      short loc_14002DD47
0x14002dd40  mov     ebx, 98000100h
0x14002dd45  jmp     short loc_14002DD66
0x14002dd47  lea     rcx, [rbp+Buf1]
0x14002dd4b  mov     qword ptr [rbp+Buf1], r15
0x14002dd4f  mov     ebx, 18000100h
0x14002dd54  mov     qword ptr [rbp+Buf1+8], r14
0x14002dd58  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002dd5d  test    al, al
0x14002dd5f  jnz     short loc_14002DD66
0x14002dd61  mov     ebx, 19000100h
0x14002dd66  movups  xmm0, xmmword ptr [rsi+8]
0x14002dd6a  mov     r8d, 10h; Size
0x14002dd70  lea     rdx, GUID_NULL; Buf2
0x14002dd77  lea     rcx, [rbp+Buf1]; Buf1
0x14002dd7b  movdqu  [rbp+Buf1], xmm0
0x14002dd80  call    memcmp_0
0x14002dd85  test    eax, eax
0x14002dd87  mov     ecx, ebx
0x14002dd89  setz    al
0x14002dd8c  bts     ecx, 7
0x14002dd90  test    al, al
0x14002dd92  cmovz   ecx, ebx
0x14002dd95  mov     [rdi+40h], ecx
0x14002dd98  add     rsp, 38h
0x14002dd9c  pop     r15
0x14002dd9e  pop     r14
0x14002dda0  pop     r13
0x14002dda2  pop     r12
0x14002dda4  pop     rdi
0x14002dda5  pop     rsi
0x14002dda6  pop     rbx
0x14002dda7  pop     rbp
0x14002dda8  retn
```
