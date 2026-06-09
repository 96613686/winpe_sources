# CWcnThreadpoolSession::SendOutgoingMessage(tagWCN_MESSAGE_TYPE,tagWCN_ACTION,CSbMessageBuffer const *)

- ea: `0x1800569f0`
- end: `0x180056ad5`
- name: `?SendOutgoingMessage@CWcnThreadpoolSession@@UEAAJW4tagWCN_MESSAGE_TYPE@@W4tagWCN_ACTION@@PEBVCSbMessageBuffer@@@Z`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180053004`
- `0x1800569f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180056a82`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180056a82`

## pseudocode

```c
__int64 __fastcall CWcnThreadpoolSession::SendOutgoingMessage(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  struct _TP_WORK *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r10

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 16, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    v10 = *(struct _TP_WORK **)(a1 + 72);
    *(_QWORD *)(a1 + 64) = a4;
    SubmitThreadpoolWork(v10);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v11 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v12 + 16), 18, (unsigned int)WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids, v11, 0);
    }
    return 0;
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_s(v6[2], 17, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids, "pMessage");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800569f0  mov     [rsp+arg_0], rbx
0x1800569f5  mov     [rsp+arg_8], rsi
0x1800569fa  push    rdi
0x1800569fb  sub     rsp, 30h
0x1800569ff  mov     rbx, r9
0x180056a02  mov     rdi, rcx
0x180056a05  mov     r10, cs:WPP_GLOBAL_Control
0x180056a0c  lea     rsi, WPP_GLOBAL_Control
0x180056a13  cmp     r10, rsi
0x180056a16  jz      short loc_180056A48
0x180056a18  cmp     byte ptr [r10+19h], 6
0x180056a1d  jb      short loc_180056A48
0x180056a1f  mov     ecx, 1; int
0x180056a24  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180056a29  mov     rcx, [r10+10h]
0x180056a2d  lea     r8, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids
0x180056a34  mov     edx, 10h
0x180056a39  mov     r9, rax
0x180056a3c  call    WPP_SF_s
0x180056a41  mov     r10, cs:WPP_GLOBAL_Control
0x180056a48  test    rbx, rbx
0x180056a4b  jnz     short loc_180056A7A
0x180056a4d  cmp     r10, rsi
0x180056a50  jz      short loc_180056A73
0x180056a52  cmp     byte ptr [r10+19h], 2
0x180056a57  jb      short loc_180056A73
0x180056a59  mov     rcx, [r10+10h]
0x180056a5d  lea     edx, [rbx+11h]
0x180056a60  lea     r9, aPmessage; "pMessage"
0x180056a67  lea     r8, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids
0x180056a6e  call    WPP_SF_s
0x180056a73  mov     eax, 80004003h
0x180056a78  jmp     short loc_180056AC5
0x180056a7a  mov     rcx, [rdi+48h]; pwk
0x180056a7e  mov     [rdi+40h], rbx
0x180056a82  call    cs:__imp_SubmitThreadpoolWork
0x180056a88  mov     r10, cs:WPP_GLOBAL_Control
0x180056a8f  cmp     r10, rsi
0x180056a92  jz      short loc_180056AC3
0x180056a94  cmp     byte ptr [r10+19h], 6
0x180056a99  jb      short loc_180056AC3
0x180056a9b  or      ecx, 0FFFFFFFFh; int
0x180056a9e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180056aa3  mov     rcx, [r10+10h]
0x180056aa7  lea     r8, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids
0x180056aae  mov     edx, 12h
0x180056ab3  mov     [rsp+38h+var_18], 0
0x180056abb  mov     r9, rax
0x180056abe  call    WPP_SF_sd
0x180056ac3  xor     eax, eax
0x180056ac5  mov     rbx, [rsp+38h+arg_0]
0x180056aca  mov     rsi, [rsp+38h+arg_8]
0x180056acf  add     rsp, 30h
0x180056ad3  pop     rdi
0x180056ad4  retn
```
