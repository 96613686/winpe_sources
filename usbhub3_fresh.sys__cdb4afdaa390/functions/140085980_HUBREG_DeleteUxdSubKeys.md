# HUBREG_DeleteUxdSubKeys

- ea: `0x140085980`
- end: `0x140085b8c`
- name: `HUBREG_DeleteUxdSubKeys`
- size: `524`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14008af98`

## callees

- `0x1400067ac`
- `0x140045530`
- `0x140045570`
- `0x140045940`
- `0x140085980`

## import_xrefs

- `ntoskrnl!ZwEnumerateValueKey` at `0x140085a78`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140085a78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085b56`
- `ntoskrnl!ExAllocatePool2` at `0x1400859fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400859fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085aa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085aa5`

## pseudocode

```c
__int64 __fastcall HUBREG_DeleteUxdSubKeys(__int64 a1, __int64 a2, __int64 a3)
{
  void *v6; // r15
  int v7; // edx
  _OWORD *Pool2; // rdi
  ULONG v9; // ebx
  ULONG v10; // esi
  ULONG ResultLength; // [rsp+40h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-A0h] BYREF
  _DWORD v14[20]; // [rsp+60h] [rbp-88h] BYREF

  memset(v14, 0, 0x44u);
  ResultLength = 0;
  DestinationString = 0;
  v6 = (void *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1856))(
                 WdfDriverGlobals,
                 a3);
  Pool2 = (_OWORD *)ExAllocatePool2(64, 42, 1748191317);
  if ( Pool2 )
  {
    v9 = 0;
    while ( 1 )
    {
      *Pool2 = 0;
      Pool2[1] = 0;
      *(_OWORD *)((char *)Pool2 + 26) = 0;
      if ( ZwEnumerateValueKey(v6, v9, KeyValueBasicInformation, Pool2, 0x2Au, &ResultLength) < 0 )
        break;
      v10 = v9++;
      if ( *((_DWORD *)Pool2 + 1) == 3 )
      {
        *((_WORD *)Pool2 + 18) = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)Pool2 + 6);
        memset(v14, 0, 0x44u);
        if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, _DWORD *, _QWORD, _QWORD))(WdfFunctions_01015 + 1880))(
               WdfDriverGlobals,
               a3,
               &DestinationString,
               68,
               v14,
               0,
               0) < 0 )
          break;
        if ( v14[9] == 1 || (*(_DWORD *)(a2 + 4) & 0x100) != 0 )
        {
          if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1872))(
                 WdfDriverGlobals,
                 a3,
                 &DestinationString) < 0 )
            break;
          v9 = v10;
        }
      }
    }
    ExFreePoolWithTag(Pool2, 0x68334855u);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 2536), v7, 3, 113, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140085980  mov     [rsp+arg_8], rbx
0x140085985  push    rbp
0x140085986  push    rsi
0x140085987  push    rdi
0x140085988  push    r14
0x14008598a  push    r15
0x14008598c  sub     rsp, 0C0h
0x140085993  mov     rax, cs:__security_cookie
0x14008599a  xor     rax, rsp
0x14008599d  mov     [rsp+0E8h+var_38], rax
0x1400859a5  mov     r14, rdx
0x1400859a8  mov     rbp, r8
0x1400859ab  xor     edx, edx; Val
0x1400859ad  mov     rbx, rcx
0x1400859b0  lea     rcx, [rsp+0E8h+var_88]; void *
0x1400859b5  lea     r8d, [rdx+44h]; Size
0x1400859b9  call    memset
0x1400859be  mov     rax, cs:WdfFunctions_01015
0x1400859c5  xorps   xmm0, xmm0
0x1400859c8  mov     rcx, cs:WdfDriverGlobals
0x1400859cf  mov     rdx, rbp
0x1400859d2  mov     [rsp+0E8h+var_A8], 0
0x1400859da  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1400859df  mov     rax, [rax+740h]
0x1400859e6  call    _guard_dispatch_icall
0x1400859eb  mov     edx, 2Ah ; '*'
0x1400859f0  mov     r8d, 68334855h
0x1400859f6  mov     r15, rax
0x1400859f9  lea     ecx, [rdx+16h]
0x1400859fc  call    cs:__imp_ExAllocatePool2
0x140085a03  nop     dword ptr [rax+rax+00h]
0x140085a08  mov     rdi, rax
0x140085a0b  test    rax, rax
0x140085a0e  jnz     short loc_140085A4B
0x140085a10  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140085a17  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140085a1e  jz      loc_140085B62
0x140085a24  mov     rcx, [rbx+9E8h]
0x140085a2b  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140085a32  lea     r9d, [rdi+71h]
0x140085a36  mov     qword ptr [rsp+0E8h+Length], rax
0x140085a3b  lea     r8d, [rdi+3]
0x140085a3f  mov     dl, 2
0x140085a41  call    WPP_RECORDER_SF_
0x140085a46  jmp     loc_140085B62
0x140085a4b  xor     ebx, ebx
0x140085a4d  xorps   xmm0, xmm0
0x140085a50  lea     rax, [rsp+0E8h+var_A8]
0x140085a55  movups  xmmword ptr [rdi], xmm0
0x140085a58  mov     [rsp+0E8h+ResultLength], rax; ResultLength
0x140085a5d  mov     r9, rdi; KeyValueInformation
0x140085a60  movups  xmmword ptr [rdi+10h], xmm0
0x140085a64  xor     r8d, r8d; KeyValueInformationClass
0x140085a67  mov     [rsp+0E8h+Length], 2Ah ; '*'; Length
0x140085a6f  mov     edx, ebx; Index
0x140085a71  mov     rcx, r15; KeyHandle
0x140085a74  movups  xmmword ptr [rdi+1Ah], xmm0
0x140085a78  call    cs:__imp_ZwEnumerateValueKey
0x140085a7f  nop     dword ptr [rax+rax+00h]
0x140085a84  test    eax, eax
0x140085a86  js      loc_140085B4E
0x140085a8c  mov     esi, ebx
0x140085a8e  inc     ebx
0x140085a90  cmp     dword ptr [rdi+4], 3
0x140085a94  jnz     short loc_140085A4D
0x140085a96  xor     eax, eax
0x140085a98  lea     rdx, [rdi+0Ch]; SourceString
0x140085a9c  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x140085aa1  mov     [rdi+24h], ax
0x140085aa5  call    cs:__imp_RtlInitUnicodeString
0x140085aac  nop     dword ptr [rax+rax+00h]
0x140085ab1  xor     edx, edx; Val
0x140085ab3  lea     rcx, [rsp+0E8h+var_88]; void *
0x140085ab8  lea     r8d, [rdx+44h]; Size
0x140085abc  call    memset
0x140085ac1  mov     rax, cs:WdfFunctions_01015
0x140085ac8  lea     rcx, [rsp+0E8h+var_88]
0x140085acd  mov     [rsp+0E8h+var_B8], 0
0x140085ad6  lea     r8, [rsp+0E8h+DestinationString]
0x140085adb  mov     [rsp+0E8h+ResultLength], 0
0x140085ae4  mov     r9d, 44h ; 'D'
0x140085aea  mov     qword ptr [rsp+0E8h+Length], rcx
0x140085aef  mov     rdx, rbp
0x140085af2  mov     rax, [rax+758h]
0x140085af9  mov     rcx, cs:WdfDriverGlobals
0x140085b00  call    _guard_dispatch_icall
0x140085b05  test    eax, eax
0x140085b07  js      short loc_140085B4E
0x140085b09  cmp     [rsp+0E8h+var_64], 1
0x140085b11  jz      short loc_140085B21
0x140085b13  test    dword ptr [r14+4], 100h
0x140085b1b  jz      loc_140085A4D
0x140085b21  mov     rax, cs:WdfFunctions_01015
0x140085b28  lea     r8, [rsp+0E8h+DestinationString]
0x140085b2d  mov     rcx, cs:WdfDriverGlobals
0x140085b34  mov     rdx, rbp
0x140085b37  mov     rax, [rax+750h]
0x140085b3e  call    _guard_dispatch_icall
0x140085b43  test    eax, eax
0x140085b45  js      short loc_140085B4E
0x140085b47  mov     ebx, esi
0x140085b49  jmp     loc_140085A4D
0x140085b4e  mov     edx, 68334855h; Tag
0x140085b53  mov     rcx, rdi; P
0x140085b56  call    cs:__imp_ExFreePoolWithTag
0x140085b5d  nop     dword ptr [rax+rax+00h]
0x140085b62  xor     eax, eax
0x140085b64  mov     rcx, [rsp+0E8h+var_38]
0x140085b6c  xor     rcx, rsp; StackCookie
0x140085b6f  call    __security_check_cookie
0x140085b74  mov     rbx, [rsp+0E8h+arg_8]
0x140085b7c  add     rsp, 0C0h
0x140085b83  pop     r15
0x140085b85  pop     r14
0x140085b87  pop     rdi
0x140085b88  pop     rsi
0x140085b89  pop     rbp
0x140085b8a  retn
```
