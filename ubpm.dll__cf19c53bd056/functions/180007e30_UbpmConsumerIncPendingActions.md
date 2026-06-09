# UbpmConsumerIncPendingActions

- ea: `0x180007e30`
- end: `0x180008028`
- name: `UbpmConsumerIncPendingActions`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002dc0`
- `0x180003684`
- `0x180007480`
- `0x18000a710`
- `0x180019a30`
- `0x180026650`
- `0x1800275a0`
- `0x18002b2b0`
- `0x18002b880`

## callees

- `0x180007e30`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007e5f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007e5f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007ffc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007ffc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007fee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007fee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e65`

## pseudocode

```c
__int64 __fastcall UbpmConsumerIncPendingActions(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  int v4; // eax
  __int64 v5; // rax
  int *v6; // rcx
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
  int *v20; // [rsp+80h] [rbp-19h]
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
  if ( (unsigned int)dword_18004C0F0 > 5 && (qword_18004C100 & 1) != 0 && (qword_18004C108 & 1) == qword_18004C108 )
  {
    v4 = *(_DWORD *)(a1 + 92) & 1;
    v14 = a1;
    v12 = v4;
    v13[0] = *(_DWORD *)(a1 + 88);
    v5 = *(_QWORD *)(a1 + 24);
    v11 = v2;
    v30 = 8;
    v28 = 4;
    v6 = *(int **)(v5 + 8);
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
      v6 = &dword_1800405F4;
      v9 = 2;
    }
    v21 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v20 = v6;
    v22 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v17 = &dword_180042DFC;
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
0x180007e30  mov     [rsp-8+arg_8], rbx
0x180007e35  mov     [rsp-8+arg_10], rsi
0x180007e3a  push    rbp
0x180007e3b  push    rdi
0x180007e3c  push    r14
0x180007e3e  lea     rbp, [rsp-47h]
0x180007e43  sub     rsp, 0E0h
0x180007e4a  mov     rax, cs:__security_cookie
0x180007e51  xor     rax, rsp
0x180007e54  mov     [rbp+57h+var_20], rax
0x180007e58  mov     rbx, rcx
0x180007e5b  add     rcx, 48h ; 'H'
0x180007e5f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007e65  call    cs:__imp_GetCurrentThreadId
0x180007e6b  xor     r14d, r14d
0x180007e6e  mov     [rbx+50h], eax
0x180007e71  test    byte ptr [rbx+5Ch], 1
0x180007e75  jz      short loc_180007E7E
0x180007e77  mov     edi, 4D3h
0x180007e7c  jmp     short loc_180007E97
0x180007e7e  mov     eax, [rbx+58h]
0x180007e81  cmp     eax, 2710h
0x180007e86  jl      short loc_180007E8F
0x180007e88  mov     edi, 54h ; 'T'
0x180007e8d  jmp     short loc_180007E97
0x180007e8f  inc     eax
0x180007e91  mov     edi, r14d
0x180007e94  mov     [rbx+58h], eax
0x180007e97  mov     eax, cs:dword_18004C0F0
0x180007e9d  cmp     eax, 5
0x180007ea0  jbe     loc_180007FF4
0x180007ea6  mov     rcx, cs:qword_18004C108
0x180007ead  mov     rax, cs:qword_18004C100
0x180007eb4  test    al, 1
0x180007eb6  jz      loc_180007FF4
0x180007ebc  mov     rax, rcx
0x180007ebf  and     eax, 1
0x180007ec2  cmp     rax, rcx
0x180007ec5  jnz     loc_180007FF4
0x180007ecb  mov     eax, [rbx+5Ch]
0x180007ece  and     eax, 1
0x180007ed1  mov     [rbp+57h+var_B0], rbx
0x180007ed5  mov     [rbp+57h+var_BC], eax
0x180007ed8  mov     eax, [rbx+58h]
0x180007edb  mov     [rbp+57h+var_B8], eax
0x180007ede  mov     rax, [rbx+18h]
0x180007ee2  mov     [rbp+57h+var_C0], edi
0x180007ee5  mov     [rbp+57h+var_28], 8
0x180007eed  mov     [rbp+57h+var_38], 4
0x180007ef5  mov     rcx, [rax+8]
0x180007ef9  lea     rax, [rbp+57h+var_B0]
0x180007efd  mov     [rbp+57h+var_30], rax
0x180007f01  lea     rax, [rbp+57h+var_C0]
0x180007f05  mov     [rbp+57h+var_40], rax
0x180007f09  lea     rax, [rbp+57h+var_BC]
0x180007f0d  mov     [rbp+57h+var_50], rax
0x180007f11  lea     rax, [rbp+57h+var_B8]
0x180007f15  mov     [rbp+57h+var_60], rax
0x180007f19  mov     [rbp+57h+var_48], 4
0x180007f21  mov     [rbp+57h+var_58], 4
0x180007f29  test    rcx, rcx
0x180007f2c  jz      short loc_180007F55
0x180007f2e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007f35  nop     word ptr [rax+rax+00000000h]
0x180007f40  cmp     [rcx+rax*2+2], r14w
0x180007f46  lea     rax, [rax+1]
0x180007f4a  jnz     short loc_180007F40
0x180007f4c  lea     eax, ds:2[rax*2]
0x180007f53  jmp     short loc_180007F61
0x180007f55  lea     rcx, dword_1800405F4
0x180007f5c  mov     eax, 2
0x180007f61  mov     [rbp+57h+var_68], eax
0x180007f64  xor     r9d, r9d; RelatedActivityId
0x180007f67  movzx   eax, cs:word_180042DF2
0x180007f6e  xor     r8d, r8d; ActivityId
0x180007f71  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180007f74  mov     rax, cs:off_18004C0F8
0x180007f7b  mov     [rbp+57h+var_90.Ptr], rax
0x180007f7f  mov     [rbp+57h+var_70], rcx
0x180007f83  lea     rcx, _TraceLoggingMetadata
0x180007f8a  mov     [rbp+57h+var_64], r14d
0x180007f8e  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180007f95  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180007f9d  movzx   eax, word ptr [rax]
0x180007fa0  mov     [rbp+57h+var_90.Size], eax
0x180007fa3  lea     rax, dword_180042DFC
0x180007faa  mov     [rbp+57h+var_80], rax
0x180007fae  lea     rax, _TraceLoggingMetadataEnd
0x180007fb5  sub     eax, ecx
0x180007fb7  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180007fbe  mov     [rbp+57h+var_78], 91h
0x180007fc5  mov     [rbp+57h+var_74], 1
0x180007fcc  mov     [rbp+57h+var_B4], eax
0x180007fcf  lea     rax, [rbp+57h+var_90]
0x180007fd3  mov     edx, [rbp+57h+var_B4]
0x180007fd6  mov     rcx, cs:RegHandle; RegHandle
0x180007fdd  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180007fe1  mov     [rsp+0F0h+UserData], rax; UserData
0x180007fe6  mov     [rsp+0F0h+UserDataCount], 7; UserDataCount
0x180007fee  call    cs:__imp_EventWriteTransfer
0x180007ff4  lea     rcx, [rbx+48h]
0x180007ff8  mov     [rbx+50h], r14d
0x180007ffc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008002  mov     eax, edi
0x180008004  mov     rcx, [rbp+57h+var_20]
0x180008008  xor     rcx, rsp; StackCookie
0x18000800b  call    __security_check_cookie
0x180008010  lea     r11, [rsp+0F0h+var_10]
0x180008018  mov     rbx, [r11+28h]
0x18000801c  mov     rsi, [r11+30h]
0x180008020  mov     rsp, r11
0x180008023  pop     r14
0x180008025  pop     rdi
0x180008026  pop     rbp
0x180008027  retn
```
