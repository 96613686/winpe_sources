# UbpmConsumerIncPendingActions

- ea: `0x180008920`
- end: `0x180008b26`
- name: `UbpmConsumerIncPendingActions`
- size: `518`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ec0`
- `0x180003100`
- `0x180007ec0`
- `0x18000f880`
- `0x180011480`
- `0x1800282b0`
- `0x1800293d0`
- `0x18002d260`
- `0x18002d890`

## callees

- `0x180008920`
- `0x180040260`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000894f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000894f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008af3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008af3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008adf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000895b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000895b`

## pseudocode

```c
__int64 __fastcall UbpmConsumerIncPendingActions(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  int v4; // eax
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v9; // eax
  unsigned int v11; // [rsp+30h] [rbp-69h] BYREF
  int v12; // [rsp+34h] [rbp-65h] BYREF
  _DWORD v13[2]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v14; // [rsp+40h] [rbp-59h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  int *v17; // [rsp+70h] [rbp-29h]
  int v18; // [rsp+78h] [rbp-21h]
  int v19; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v20; // [rsp+80h] [rbp-19h]
  int v21; // [rsp+88h] [rbp-11h]
  int v22; // [rsp+8Ch] [rbp-Dh]
  _DWORD *v23; // [rsp+90h] [rbp-9h]
  __int64 v24; // [rsp+98h] [rbp-1h]
  int *v25; // [rsp+A0h] [rbp+7h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]
  unsigned int *v27; // [rsp+B0h] [rbp+17h]
  __int64 v28; // [rsp+B8h] [rbp+1Fh]
  __int64 *v29; // [rsp+C0h] [rbp+27h]
  __int64 v30; // [rsp+C8h] [rbp+2Fh]

  RtlAcquireSRWLockExclusive(a1 + 72);
  *(_DWORD *)(a1 + 80) = GetCurrentThreadId();
  if ( (*(_BYTE *)(a1 + 92) & 1) != 0 )
  {
    v2 = 1235;
  }
  else
  {
    v3 = *(_DWORD *)(a1 + 88);
    if ( v3 < 10000 )
    {
      v2 = 0;
      *(_DWORD *)(a1 + 88) = v3 + 1;
    }
    else
    {
      v2 = 84;
    }
  }
  if ( (unsigned int)dword_18004F0F0 > 5 && (qword_18004F100 & 1) != 0 && (qword_18004F108 & 1) == qword_18004F108 )
  {
    v4 = *(_DWORD *)(a1 + 92) & 1;
    v14 = a1;
    v12 = v4;
    v13[0] = *(_DWORD *)(a1 + 88);
    v5 = *(_QWORD *)(a1 + 24);
    v11 = v2;
    v30 = 8;
    v28 = 4;
    v6 = *(__int64 **)(v5 + 8);
    v29 = &v14;
    v27 = &v11;
    v25 = &v12;
    v23 = v13;
    v26 = 4;
    v24 = 4;
    if ( v6 )
    {
      v7 = -1;
      while ( *((_WORD *)v6 + ++v7) != 0 )
        ;
      v9 = 2 * v7 + 2;
    }
    else
    {
      v6 = &qword_1800439C0;
      v9 = 2;
    }
    v21 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v20 = v6;
    v22 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v17 = &dword_180045E64;
    UserData.Reserved = 2;
    v18 = 145;
    v19 = 1;
    v13[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
  }
  *(_DWORD *)(a1 + 80) = 0;
  RtlReleaseSRWLockExclusive(a1 + 72);
  return v2;
}

```

## disassembly

```asm
0x180008920  mov     [rsp-8+arg_8], rbx
0x180008925  mov     [rsp-8+arg_10], rsi
0x18000892a  push    rbp
0x18000892b  push    rdi
0x18000892c  push    r14
0x18000892e  lea     rbp, [rsp-47h]
0x180008933  sub     rsp, 0E0h
0x18000893a  mov     rax, cs:__security_cookie
0x180008941  xor     rax, rsp
0x180008944  mov     [rbp+57h+var_20], rax
0x180008948  mov     rbx, rcx
0x18000894b  add     rcx, 48h ; 'H'
0x18000894f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008956  nop     dword ptr [rax+rax+00h]
0x18000895b  call    cs:__imp_GetCurrentThreadId
0x180008962  nop     dword ptr [rax+rax+00h]
0x180008967  xor     r14d, r14d
0x18000896a  mov     [rbx+50h], eax
0x18000896d  test    byte ptr [rbx+5Ch], 1
0x180008971  jz      short loc_18000897A
0x180008973  mov     edi, 4D3h
0x180008978  jmp     short loc_180008993
0x18000897a  mov     eax, [rbx+58h]
0x18000897d  cmp     eax, 2710h
0x180008982  jl      short loc_18000898B
0x180008984  mov     edi, 54h ; 'T'
0x180008989  jmp     short loc_180008993
0x18000898b  inc     eax
0x18000898d  mov     edi, r14d
0x180008990  mov     [rbx+58h], eax
0x180008993  mov     eax, cs:dword_18004F0F0
0x180008999  cmp     eax, 5
0x18000899c  jbe     loc_180008AEB
0x1800089a2  mov     rcx, cs:qword_18004F108
0x1800089a9  mov     rax, cs:qword_18004F100
0x1800089b0  test    al, 1
0x1800089b2  jz      loc_180008AEB
0x1800089b8  mov     rax, rcx
0x1800089bb  and     eax, 1
0x1800089be  cmp     rax, rcx
0x1800089c1  jnz     loc_180008AEB
0x1800089c7  mov     eax, [rbx+5Ch]
0x1800089ca  and     eax, 1
0x1800089cd  mov     [rbp+57h+var_B0], rbx
0x1800089d1  mov     [rbp+57h+var_BC], eax
0x1800089d4  mov     eax, [rbx+58h]
0x1800089d7  mov     [rbp+57h+var_B8], eax
0x1800089da  mov     rax, [rbx+18h]
0x1800089de  mov     [rbp+57h+var_C0], edi
0x1800089e1  mov     [rbp+57h+var_28], 8
0x1800089e9  mov     [rbp+57h+var_38], 4
0x1800089f1  mov     rcx, [rax+8]
0x1800089f5  lea     rax, [rbp+57h+var_B0]
0x1800089f9  mov     [rbp+57h+var_30], rax
0x1800089fd  lea     rax, [rbp+57h+var_C0]
0x180008a01  mov     [rbp+57h+var_40], rax
0x180008a05  lea     rax, [rbp+57h+var_BC]
0x180008a09  mov     [rbp+57h+var_50], rax
0x180008a0d  lea     rax, [rbp+57h+var_B8]
0x180008a11  mov     [rbp+57h+var_60], rax
0x180008a15  mov     [rbp+57h+var_48], 4
0x180008a1d  mov     [rbp+57h+var_58], 4
0x180008a25  test    rcx, rcx
0x180008a28  jz      short loc_180008A46
0x180008a2a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008a31  cmp     [rcx+rax*2+2], r14w
0x180008a37  lea     rax, [rax+1]
0x180008a3b  jnz     short loc_180008A31
0x180008a3d  lea     eax, ds:2[rax*2]
0x180008a44  jmp     short loc_180008A52
0x180008a46  lea     rcx, qword_1800439C0
0x180008a4d  mov     eax, 2
0x180008a52  mov     [rbp+57h+var_68], eax
0x180008a55  xor     r9d, r9d; RelatedActivityId
0x180008a58  movzx   eax, cs:word_180045E5A
0x180008a5f  xor     r8d, r8d; ActivityId
0x180008a62  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180008a65  mov     rax, cs:off_18004F0F8
0x180008a6c  mov     [rbp+57h+var_90.Ptr], rax
0x180008a70  mov     [rbp+57h+var_70], rcx
0x180008a74  lea     rcx, _TraceLoggingMetadata
0x180008a7b  mov     [rbp+57h+var_64], r14d
0x180008a7f  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180008a86  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180008a8e  movzx   eax, word ptr [rax]
0x180008a91  mov     [rbp+57h+var_90.Size], eax
0x180008a94  lea     rax, dword_180045E64
0x180008a9b  mov     [rbp+57h+var_80], rax
0x180008a9f  lea     rax, _TraceLoggingMetadataEnd
0x180008aa6  sub     eax, ecx
0x180008aa8  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180008aaf  mov     [rbp+57h+var_78], 91h
0x180008ab6  mov     [rbp+57h+var_74], 1
0x180008abd  mov     [rbp+57h+var_B4], eax
0x180008ac0  lea     rax, [rbp+57h+var_90]
0x180008ac4  mov     edx, [rbp+57h+var_B4]
0x180008ac7  mov     rcx, cs:RegHandle; RegHandle
0x180008ace  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180008ad2  mov     [rsp+0F0h+UserData], rax; UserData
0x180008ad7  mov     [rsp+0F0h+UserDataCount], 7; UserDataCount
0x180008adf  call    cs:__imp_EventWriteTransfer
0x180008ae6  nop     dword ptr [rax+rax+00h]
0x180008aeb  lea     rcx, [rbx+48h]
0x180008aef  mov     [rbx+50h], r14d
0x180008af3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008afa  nop     dword ptr [rax+rax+00h]
0x180008aff  mov     eax, edi
0x180008b01  mov     rcx, [rbp+57h+var_20]
0x180008b05  xor     rcx, rsp; StackCookie
0x180008b08  call    __security_check_cookie
0x180008b0d  lea     r11, [rsp+0F0h+var_10]
0x180008b15  mov     rbx, [r11+28h]
0x180008b19  mov     rsi, [r11+30h]
0x180008b1d  mov     rsp, r11
0x180008b20  pop     r14
0x180008b22  pop     rdi
0x180008b23  pop     rbp
0x180008b24  retn
```
