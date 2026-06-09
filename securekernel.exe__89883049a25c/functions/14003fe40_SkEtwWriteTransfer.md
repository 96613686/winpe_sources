# SkEtwWriteTransfer

- ea: `0x14003fe40`
- end: `0x14003ffb3`
- name: `SkEtwWriteTransfer`
- size: `371`
- prototype: `NTSTATUS __stdcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140001040`
- `0x14003fc48`
- `0x14009a77c`

## callees

- `0x14003fe40`
- `0x140040158`
- `0x1400b7188`
- `0x1400b71b8`
- `0x1400b7674`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
NTSTATUS __stdcall SkEtwWriteTransfer(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  __int64 v8; // rbx
  NTSTATUS v9; // edi
  __int64 v10; // rsi
  __int64 SyscallBuffer; // rax
  __int64 v13; // [rsp+38h] [rbp-69h] BYREF
  PCEVENT_DESCRIPTOR v14; // [rsp+40h] [rbp-61h]
  unsigned int v15; // [rsp+48h] [rbp-59h] BYREF
  REGHANDLE v16; // [rsp+50h] [rbp-51h]
  EVENT_DESCRIPTOR v17; // [rsp+58h] [rbp-49h]
  GUID v18; // [rsp+68h] [rbp-39h]
  GUID v19; // [rsp+78h] [rbp-29h]
  __int64 v20; // [rsp+88h] [rbp-19h]
  __int64 v21; // [rsp+90h] [rbp-11h]

  v14 = EventDescriptor;
  memset_0(&v15, 0, 0x68u);
  v8 = 0;
  v13 = 0;
  if ( UserDataCount )
  {
    v9 = SkpEtwMarshalEventDataDescriptor(UserDataCount, UserData, 0, 0, &v13);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741789 )
      return v9;
    v10 = v13;
    SyscallBuffer = SkAllocateSyscallBuffer((unsigned int)v13, 0);
    v8 = SyscallBuffer;
    if ( !SyscallBuffer )
      return -1073741670;
    v9 = SkpEtwMarshalEventDataDescriptor(UserDataCount, UserData, SyscallBuffer, v10, 0);
    if ( v9 < 0 )
    {
LABEL_12:
      SkFreeSyscallBuffer(v8);
      return v9;
    }
  }
  memset_0(&v15, 0, 0x68u);
  HIWORD(v15) = 21;
  v16 = RegHandle;
  v17 = *v14;
  if ( ActivityId )
    v18 = *ActivityId;
  if ( RelatedActivityId )
    v19 = *RelatedActivityId;
  v20 = UserDataCount;
  v21 = IumSyscallNormalAddress(v8);
  SkCallNormalMode(&v15);
  v9 = v16;
  if ( v8 )
    goto LABEL_12;
  return v9;
}

```

## disassembly

```asm
0x14003fe40  mov     rax, rsp
0x14003fe43  mov     [rax+10h], rbx
0x14003fe47  mov     [rax+18h], rsi
0x14003fe4b  mov     [rax+8], rcx
0x14003fe4f  push    rbp
0x14003fe50  push    rdi
0x14003fe51  push    r12
0x14003fe53  push    r13
0x14003fe55  push    r14
0x14003fe57  lea     rbp, [rax-4Fh]
0x14003fe5b  sub     rsp, 0C0h
0x14003fe62  mov     rax, cs:__security_cookie
0x14003fe69  xor     rax, rsp
0x14003fe6c  mov     [rbp+47h+var_30], rax
0x14003fe70  mov     r13, [rbp+47h+UserData]
0x14003fe74  lea     rcx, [rbp+47h+var_A0]; void *
0x14003fe78  mov     [rbp+47h+var_A8], rdx
0x14003fe7c  mov     r12, r8
0x14003fe7f  xor     edx, edx; Val
0x14003fe81  mov     r14, r9
0x14003fe84  lea     r8d, [rdx+68h]; Size
0x14003fe88  call    memset_0
0x14003fe8d  xor     esi, esi
0x14003fe8f  xor     ebx, ebx
0x14003fe91  mov     [rbp+47h+var_B0], rsi
0x14003fe95  cmp     [rbp+47h+UserDataCount], ebx
0x14003fe98  jbe     short loc_14003FF0C
0x14003fe9a  mov     ecx, [rbp+47h+UserDataCount]
0x14003fe9d  lea     rax, [rbp+47h+var_B0]
0x14003fea1  xor     r9d, r9d
0x14003fea4  mov     [rsp+0E0h+var_C0], rax
0x14003fea9  xor     r8d, r8d
0x14003feac  mov     rdx, r13
0x14003feaf  call    SkpEtwMarshalEventDataDescriptor
0x14003feb4  mov     ecx, 80000000h
0x14003feb9  mov     edi, eax
0x14003febb  add     eax, ecx
0x14003febd  test    ecx, eax
0x14003febf  jnz     short loc_14003FECD
0x14003fec1  cmp     edi, 0C0000023h
0x14003fec7  jnz     loc_14003FF88
0x14003fecd  mov     rsi, [rbp+47h+var_B0]
0x14003fed1  xor     edx, edx
0x14003fed3  mov     ecx, esi
0x14003fed5  call    SkAllocateSyscallBuffer
0x14003feda  mov     rbx, rax
0x14003fedd  test    rax, rax
0x14003fee0  jnz     short loc_14003FEEC
0x14003fee2  mov     edi, 0C000009Ah
0x14003fee7  jmp     loc_14003FF88
0x14003feec  mov     ecx, [rbp+47h+UserDataCount]
0x14003feef  mov     r9, rsi
0x14003fef2  mov     r8, rax
0x14003fef5  mov     [rsp+0E0h+var_C0], 0
0x14003fefe  mov     rdx, r13
0x14003ff01  call    SkpEtwMarshalEventDataDescriptor
0x14003ff06  mov     edi, eax
0x14003ff08  test    eax, eax
0x14003ff0a  js      short loc_14003FF7E
0x14003ff0c  xor     edx, edx; Val
0x14003ff0e  lea     rcx, [rbp+47h+var_A0]; void *
0x14003ff12  lea     r8d, [rdx+68h]; Size
0x14003ff16  call    memset_0
0x14003ff1b  mov     eax, 15h
0x14003ff20  mov     [rbp+47h+var_9E], ax
0x14003ff24  mov     rax, [rbp+47h+arg_0]
0x14003ff28  mov     dword ptr [rbp+47h+var_98], eax
0x14003ff2b  mov     eax, dword ptr [rbp+47h+arg_0+4]
0x14003ff2e  mov     dword ptr [rbp+47h+var_98+4], eax
0x14003ff31  mov     rax, [rbp+47h+var_A8]
0x14003ff35  movups  xmm0, xmmword ptr [rax]
0x14003ff38  movdqu  [rbp+47h+var_90], xmm0
0x14003ff3d  test    r12, r12
0x14003ff40  jz      short loc_14003FF4C
0x14003ff42  movups  xmm0, xmmword ptr [r12]
0x14003ff47  movdqu  [rbp+47h+var_80], xmm0
0x14003ff4c  test    r14, r14
0x14003ff4f  jz      short loc_14003FF5A
0x14003ff51  movups  xmm0, xmmword ptr [r14]
0x14003ff55  movdqu  [rbp+47h+var_70], xmm0
0x14003ff5a  mov     eax, [rbp+47h+UserDataCount]
0x14003ff5d  mov     rcx, rbx
0x14003ff60  mov     [rbp+47h+var_60], rax
0x14003ff64  call    IumSyscallNormalAddress
0x14003ff69  lea     rcx, [rbp+47h+var_A0]
0x14003ff6d  mov     [rbp+47h+var_58], rax
0x14003ff71  call    SkCallNormalMode
0x14003ff76  mov     edi, dword ptr [rbp+47h+var_98]
0x14003ff79  test    rbx, rbx
0x14003ff7c  jz      short loc_14003FF88
0x14003ff7e  mov     edx, esi
0x14003ff80  mov     rcx, rbx
0x14003ff83  call    SkFreeSyscallBuffer
0x14003ff88  mov     eax, edi
0x14003ff8a  mov     rcx, [rbp+47h+var_30]
0x14003ff8e  xor     rcx, rsp; StackCookie
0x14003ff91  call    __security_check_cookie
0x14003ff96  lea     r11, [rsp+0E0h+var_20]
0x14003ff9e  mov     rbx, [r11+38h]
0x14003ffa2  mov     rsi, [r11+40h]
0x14003ffa6  mov     rsp, r11
0x14003ffa9  pop     r14
0x14003ffab  pop     r13
0x14003ffad  pop     r12
0x14003ffaf  pop     rdi
0x14003ffb0  pop     rbp
0x14003ffb1  retn
```
