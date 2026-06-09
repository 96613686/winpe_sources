# RtmGetOpaqueInformationPointer

- ea: `0x18000aa60`
- end: `0x18000ac14`
- name: `RtmGetOpaqueInformationPointer`
- size: `436`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_DEST_HANDLE DestHandle, PVOID *OpaqueInfoPointer)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800151ec`
- `0x1800158cc`
- `0x180015a8c`
- `0x180015f54`
- `0x180016d00`
- `0x18001decc`

## callees

- `0x180002c5c`
- `0x180002cb0`
- `0x180009d14`
- `0x18000aa60`
- `0x18001f980`

## pseudocode

```c
DWORD __stdcall RtmGetOpaqueInformationPointer(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_DEST_HANDLE DestHandle,
        PVOID *OpaqueInfoPointer)
{
  unsigned __int64 v6; // rdi
  DWORD result; // eax
  DWORD v8; // ebx
  __int64 v9; // r15
  __int128 *v10; // r9
  unsigned __int64 v11; // rsi
  __int128 *v12; // r9
  ULONG uliInst[2]; // [rsp+38h] [rbp-31h] BYREF
  __int128 v14; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-19h] BYREF
  const wchar_t *v16; // [rsp+60h] [rbp-9h]
  __int64 v17; // [rsp+68h] [rbp-1h]
  int v18; // [rsp+70h] [rbp+7h] BYREF
  __int128 v19; // [rsp+74h] [rbp+Bh]
  __int128 v20; // [rsp+84h] [rbp+1Bh]
  int v21; // [rsp+94h] [rbp+2Bh]

  *(_QWORD *)uliInst = 0;
  v18 = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v14 = 0;
  if ( (byte_18002BD1A & 8) != 0 )
  {
    v16 = L"Entered: RtmGetOpaqueInformationPointer";
    v17 = 80;
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RRAS_RTM_TRACE_INFO,
      (__int64)OpaqueInfoPointer,
      2u,
      &v15);
  }
  v6 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  *OpaqueInfoPointer = 0;
  if ( !v6 || *(_DWORD *)(v6 + 48) == 1 )
    return 6;
  GetInstance((LPSPropValue)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v6 + 16) + 16LL) + 4LL), 0, (ULONG)uliInst);
  v8 = result;
  if ( !result )
  {
    v9 = *(_QWORD *)uliInst;
    if ( (byte_18002BD1A & 8) != 0 )
    {
      LOWORD(v18) = 0;
      v10 = &v14;
      if ( *(_QWORD *)uliInst != -48 )
        v10 = (__int128 *)(*(_QWORD *)uliInst + 48LL);
      McTemplateU0zjzz_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RRAS_RTM_PARAM_TRACE_INFO,
        L"Entered: RtmGetOpaqueInformationPointer",
        (__int64)v10,
        0,
        (const wchar_t *)&v18);
    }
    if ( *(_DWORD *)(v6 + 52) != -1 )
    {
      v11 = (unsigned __int64)DestHandle ^ 0x7754DF32;
      if ( v11 )
      {
        v8 = 0;
        *OpaqueInfoPointer = (PVOID)(*(_QWORD *)(v11 + 72) + 8LL * *(int *)(v6 + 52));
      }
      else
      {
        v8 = 6;
      }
    }
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v12 = &v14;
      LOWORD(v18) = 0;
      if ( v9 != -48 )
        v12 = (__int128 *)(v9 + 48);
      McTemplateU0zjzz_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RRAS_RTM_PARAM_TRACE_INFO,
        L"Leaving: RtmGetOpaqueInformationPointer",
        (__int64)v12,
        0,
        (const wchar_t *)&v18);
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa60  mov     [rsp-8+arg_8], rbx
0x18000aa65  push    rbp
0x18000aa66  push    rsi
0x18000aa67  push    rdi
0x18000aa68  push    r14
0x18000aa6a  push    r15
0x18000aa6c  lea     rbp, [rsp-37h]
0x18000aa71  sub     rsp, 0A0h
0x18000aa78  mov     rax, cs:__security_cookie
0x18000aa7f  xor     rax, rsp
0x18000aa82  mov     [rbp+57h+var_28], rax
0x18000aa86  xor     eax, eax
0x18000aa88  mov     qword ptr [rbp+57h+uliInst], 0
0x18000aa90  test    cs:byte_18002BD1A, 8
0x18000aa97  xorps   xmm0, xmm0
0x18000aa9a  mov     rdi, rcx
0x18000aa9d  mov     [rbp+57h+var_50], eax
0x18000aaa0  mov     r14, r8
0x18000aaa3  mov     [rbp+57h+var_2C], eax
0x18000aaa6  mov     rsi, rdx
0x18000aaa9  lea     rcx, aEnteredRtmgeto; "Entered: RtmGetOpaqueInformationPointer"
0x18000aab0  movups  [rbp+57h+var_4C], xmm0
0x18000aab4  movups  [rbp+57h+var_3C], xmm0
0x18000aab8  movups  [rbp+57h+var_80], xmm0
0x18000aabc  jz      short loc_18000AAEC
0x18000aabe  mov     [rbp+57h+var_60], rcx
0x18000aac2  lea     rax, [rbp+57h+var_70]
0x18000aac6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aacd  mov     [rsp+0C0h+var_A0], rax
0x18000aad2  mov     r9d, 2
0x18000aad8  mov     [rbp+57h+var_58], 50h ; 'P'
0x18000aae0  lea     rdx, RRAS_RTM_TRACE_INFO
0x18000aae7  call    McGenEventWrite_EventWriteTransfer
0x18000aaec  xor     rdi, 7754DF32h
0x18000aaf3  mov     qword ptr [r14], 0
0x18000aafa  jz      loc_18000ABEC
0x18000ab00  cmp     dword ptr [rdi+30h], 1
0x18000ab04  jz      loc_18000ABEC
0x18000ab0a  mov     rax, [rdi+10h]
0x18000ab0e  lea     r8, [rbp+57h+uliInst]; uliInst
0x18000ab12  xor     edx, edx; lpPropSv
0x18000ab14  mov     rcx, [rax+10h]
0x18000ab18  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x18000ab1c  call    GetInstance
0x18000ab21  mov     ebx, eax
0x18000ab23  test    eax, eax
0x18000ab25  jnz     loc_18000ABF1
0x18000ab2b  test    cs:byte_18002BD1A, 8
0x18000ab32  mov     r15, qword ptr [rbp+57h+uliInst]
0x18000ab36  jz      short loc_18000AB77
0x18000ab38  mov     word ptr [rbp+57h+var_50], ax
0x18000ab3c  lea     r9, [rbp+57h+var_80]
0x18000ab40  lea     rax, [r15+30h]
0x18000ab44  test    rax, rax
0x18000ab47  lea     r8, aEnteredRtmgeto; "Entered: RtmGetOpaqueInformationPointer"
0x18000ab4e  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000ab55  cmovnz  r9, rax
0x18000ab59  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ab60  lea     rax, [rbp+57h+var_50]
0x18000ab64  mov     [rsp+0C0h+var_98], rax
0x18000ab69  mov     [rsp+0C0h+var_A0], 0
0x18000ab72  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ab77  cmp     dword ptr [rdi+34h], 0FFFFFFFFh
0x18000ab7b  jz      short loc_18000AB9E
0x18000ab7d  xor     rsi, 7754DF32h
0x18000ab84  jz      short loc_18000AB99
0x18000ab86  movsxd  rcx, dword ptr [rdi+34h]
0x18000ab8a  xor     ebx, ebx
0x18000ab8c  mov     rax, [rsi+48h]
0x18000ab90  lea     rcx, [rax+rcx*8]
0x18000ab94  mov     [r14], rcx
0x18000ab97  jmp     short loc_18000AB9E
0x18000ab99  mov     ebx, 6
0x18000ab9e  test    cs:byte_18002BD1A, 8
0x18000aba5  jz      short loc_18000ABE8
0x18000aba7  xor     eax, eax
0x18000aba9  lea     r9, [rbp+57h+var_80]
0x18000abad  mov     word ptr [rbp+57h+var_50], ax
0x18000abb1  lea     r8, aLeavingRtmgeto; "Leaving: RtmGetOpaqueInformationPointer"
0x18000abb8  lea     rax, [r15+30h]
0x18000abbc  test    rax, rax
0x18000abbf  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000abc6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000abcd  cmovnz  r9, rax
0x18000abd1  lea     rax, [rbp+57h+var_50]
0x18000abd5  mov     [rsp+0C0h+var_98], rax
0x18000abda  mov     [rsp+0C0h+var_A0], 0
0x18000abe3  call    McTemplateU0zjzz_EventWriteTransfer
0x18000abe8  mov     eax, ebx
0x18000abea  jmp     short loc_18000ABF1
0x18000abec  mov     eax, 6
0x18000abf1  mov     rcx, [rbp+57h+var_28]
0x18000abf5  xor     rcx, rsp; StackCookie
0x18000abf8  call    __security_check_cookie
0x18000abfd  mov     rbx, [rsp+0C0h+arg_8]
0x18000ac05  add     rsp, 0A0h
0x18000ac0c  pop     r15
0x18000ac0e  pop     r14
0x18000ac10  pop     rdi
0x18000ac11  pop     rsi
0x18000ac12  pop     rbp
0x18000ac13  retn
```
