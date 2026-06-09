# MpSendAsyncPanicModeMessage

- ea: `0x14007c758`
- end: `0x14007cb50`
- name: `MpSendAsyncPanicModeMessage`
- size: `1016`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140035130`
- `0x140056dc0`
- `0x14006488c`
- `0x140072dcc`
- `0x14007cd90`
- `0x140082380`

## callees

- `0x1400018a4`
- `0x140004754`
- `0x1400051bc`
- `0x140034b50`
- `0x140035080`
- `0x140035e50`
- `0x140066180`
- `0x140070414`
- `0x14007c62c`
- `0x14007c758`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007c9ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007c9ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007c9ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007c9ae`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007c934`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007c934`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007c91f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007c91f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007c7db`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007c7db`

## pseudocode

```c
__int64 __fastcall MpSendAsyncPanicModeMessage(int a1, const UNICODE_STRING *a2, char a3, char a4, int a5)
{
  char v5; // al
  unsigned int v7; // ebp
  unsigned int v8; // r13d
  unsigned int v9; // r14d
  unsigned int v10; // r15d
  const UNICODE_STRING *v11; // rsi
  int Length; // eax
  int ProcessName; // eax
  int v14; // eax
  int v15; // ebx
  __int64 v16; // rdi
  unsigned int v17; // r12d
  ULONG_PTR v18; // rbx
  int v19; // eax
  int v20; // eax
  const UNICODE_STRING *v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+38h] [rbp-60h] BYREF
  HANDLE CurrentProcessId; // [rsp+40h] [rbp-58h]
  unsigned int v26; // [rsp+A8h] [rbp+10h]

  v5 = a4;
  v23 = 0;
  CurrentProcessId = 0;
  v7 = 0;
  v26 = 0;
  v8 = 0;
  v22 = 0;
  v9 = 88;
  v10 = 0;
  v11 = 0;
  if ( a2 && a2->Buffer )
  {
    Length = a2->Length;
    if ( (_WORD)Length )
    {
      v9 = Length + 90;
      v8 = 88;
      v7 = Length + 2;
    }
    v5 = a4;
  }
  if ( a3 || v5 )
  {
    CurrentProcessId = PsGetCurrentProcessId();
    ProcessName = MpGetProcessName(CurrentProcessId, &v22);
    if ( ProcessName < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        87,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)ProcessName);
    }
    v11 = v22;
    if ( v22 )
    {
      if ( v22->Buffer )
      {
        v14 = v22->Length;
        if ( (_WORD)v14 )
        {
          v10 = v14 + 2;
          v9 += v14 + 2;
          v26 = v7 + 88;
        }
      }
    }
  }
  v15 = MpAsyncCreateNotification(&v23, v9);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        90,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        KeGetCurrentThread(),
        v15);
    }
  }
  else
  {
    _mm_lfence();
    v16 = v23;
    if ( v7 )
    {
      _mm_lfence();
      if ( RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)(v23 + v8), v7, a2) < 0 )
      {
        v7 = 0;
        v8 = 0;
      }
    }
    if ( v10 )
    {
      _mm_lfence();
      v17 = v26;
      if ( RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)(v16 + v26), v10, v11) < 0 )
      {
        v10 = 0;
        v17 = 0;
      }
    }
    else
    {
      v17 = v26;
    }
    *(_QWORD *)(v16 + 32) = MEMORY[0xFFFFF78000000014];
    *(_DWORD *)(v16 + 24) = a1;
    *(_BYTE *)(v16 + 28) = a3;
    *(_BYTE *)(v16 + 29) = a4;
    *(_DWORD *)(v16 + 60) = a5;
    v18 = MpData;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v18 + 752), 1u);
    *(_DWORD *)(v16 + 64) = *(_DWORD *)(MpData + 608);
    *(_DWORD *)(v16 + 68) = *(_DWORD *)(MpData + 612);
    *(_DWORD *)(v16 + 72) = *(_DWORD *)(MpData + 616);
    *(_DWORD *)(v16 + 76) = *(_DWORD *)(MpData + 620);
    *(_DWORD *)(v16 + 80) = *(_DWORD *)(MpData + 224);
    *(_DWORD *)(v16 + 84) = *(_DWORD *)(MpData + 220);
    ExReleaseResourceLite((PERESOURCE)(MpData + 752));
    KeLeaveCriticalRegion();
    if ( a3 || a4 )
    {
      v19 = (int)CurrentProcessId;
      *(_DWORD *)(v16 + 48) = v8;
      *(_DWORD *)(v16 + 44) = v7;
      *(_DWORD *)(v16 + 40) = v19;
      *(_DWORD *)(v16 + 56) = v17;
      *(_DWORD *)(v16 + 52) = v10;
    }
    *(_DWORD *)(v16 + 8) = v9;
    *(_DWORD *)(v16 + 16) = 11;
    v20 = MpPersistFilterHealthInformation(v16 + 24);
    if ( v20 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        88,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)v20);
    }
    v15 = MpAsyncSendNotification(v16, v9, a3 != 0, 1, 0);
    if ( v15 >= 0 )
    {
      _InterlockedExchange((volatile __int32 *)(MpData + 612), 0);
      _InterlockedExchange((volatile __int32 *)(MpData + 616), 0);
      _InterlockedExchange((volatile __int32 *)(MpData + 620), 0);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        89,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        KeGetCurrentThread(),
        v15);
    }
    MpAsyncDereferenceNotification(v16);
  }
  if ( v11 )
    MpFreeString(v11);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14007c758  mov     r11, rsp
0x14007c75b  mov     [r11+20h], r9b
0x14007c75f  mov     [r11+18h], r8b
0x14007c763  mov     [rsp+arg_0], ecx
0x14007c767  push    rbx
0x14007c768  push    rbp
0x14007c769  push    rsi
0x14007c76a  push    rdi
0x14007c76b  push    r12
0x14007c76d  push    r13
0x14007c76f  push    r14
0x14007c771  push    r15
0x14007c773  sub     rsp, 58h
0x14007c777  xor     ebx, ebx
0x14007c779  mov     al, r9b
0x14007c77c  mov     [r11-60h], rbx
0x14007c780  mov     r12, rdx
0x14007c783  mov     [rsp+98h+var_58], rbx
0x14007c788  mov     ebp, ebx
0x14007c78a  mov     [rsp+98h+arg_8], ebx
0x14007c791  mov     r13d, ebx
0x14007c794  mov     [r11-68h], rbx
0x14007c798  lea     ecx, [rbx+58h]
0x14007c79b  mov     r14d, ecx
0x14007c79e  mov     r15d, ebx
0x14007c7a1  mov     esi, ebx
0x14007c7a3  test    rdx, rdx
0x14007c7a6  jz      short loc_14007C7C7
0x14007c7a8  cmp     [rdx+8], rbx
0x14007c7ac  jz      short loc_14007C7C7
0x14007c7ae  movzx   eax, word ptr [rdx]
0x14007c7b1  cmp     bx, ax
0x14007c7b4  jz      short loc_14007C7C0
0x14007c7b6  lea     r14d, [rax+5Ah]
0x14007c7ba  mov     r13d, ecx
0x14007c7bd  lea     ebp, [rax+2]
0x14007c7c0  mov     al, [rsp+98h+arg_18]
0x14007c7c7  lea     rdi, WPP_GLOBAL_Control
0x14007c7ce  test    r8b, r8b
0x14007c7d1  jnz     short loc_14007C7DB
0x14007c7d3  test    al, al
0x14007c7d5  jz      loc_14007C870
0x14007c7db  call    cs:__imp_PsGetCurrentProcessId
0x14007c7e2  nop     dword ptr [rax+rax+00h]
0x14007c7e7  mov     rcx, rax
0x14007c7ea  mov     [rsp+98h+var_58], rax
0x14007c7ef  lea     rdx, [rsp+98h+var_68]
0x14007c7f4  call    MpGetProcessName
0x14007c7f9  test    eax, eax
0x14007c7fb  jns     short loc_14007C83C
0x14007c7fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c804  lea     rdi, WPP_GLOBAL_Control
0x14007c80b  cmp     rcx, rdi
0x14007c80e  jz      short loc_14007C843
0x14007c810  mov     ecx, [rcx+2Ch]
0x14007c813  test    cl, 1
0x14007c816  jz      short loc_14007C843
0x14007c818  lfence
0x14007c81b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c822  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14007c829  mov     edx, 57h ; 'W'
0x14007c82e  mov     r9d, eax
0x14007c831  mov     rcx, [rcx+18h]
0x14007c835  call    WPP_SF_d
0x14007c83a  jmp     short loc_14007C843
0x14007c83c  lea     rdi, WPP_GLOBAL_Control
0x14007c843  mov     rsi, [rsp+98h+var_68]
0x14007c848  test    rsi, rsi
0x14007c84b  jz      short loc_14007C870
0x14007c84d  cmp     [rsi+8], rbx
0x14007c851  jz      short loc_14007C870
0x14007c853  movzx   eax, word ptr [rsi]
0x14007c856  cmp     bx, ax
0x14007c859  jz      short loc_14007C870
0x14007c85b  add     r14d, 2
0x14007c85f  lea     r15d, [rax+2]
0x14007c863  add     r14d, eax
0x14007c866  lea     eax, [rbp+58h]
0x14007c869  mov     [rsp+98h+arg_8], eax
0x14007c870  mov     edx, r14d
0x14007c873  lea     rcx, [rsp+98h+var_60]
0x14007c878  call    MpAsyncCreateNotification
0x14007c87d  mov     ebx, eax
0x14007c87f  test    eax, eax
0x14007c881  js      loc_14007CAF0
0x14007c887  lfence
0x14007c88a  mov     rdi, [rsp+98h+var_60]
0x14007c88f  test    ebp, ebp
0x14007c891  jz      short loc_14007C8AF
0x14007c893  lfence
0x14007c896  mov     ecx, r13d
0x14007c899  mov     r8, r12; SourceString
0x14007c89c  add     rcx, rdi; pszDest
0x14007c89f  mov     edx, ebp; cbDest
0x14007c8a1  call    RtlStringCbCopyUnicodeString
0x14007c8a6  test    eax, eax
0x14007c8a8  jns     short loc_14007C8AF
0x14007c8aa  xor     ebp, ebp
0x14007c8ac  xor     r13d, r13d
0x14007c8af  test    r15d, r15d
0x14007c8b2  jz      short loc_14007C8DA
0x14007c8b4  lfence
0x14007c8b7  mov     r12d, [rsp+98h+arg_8]
0x14007c8bf  mov     r8, rsi; SourceString
0x14007c8c2  mov     edx, r15d; cbDest
0x14007c8c5  lea     rcx, [rdi+r12]; pszDest
0x14007c8c9  call    RtlStringCbCopyUnicodeString
0x14007c8ce  test    eax, eax
0x14007c8d0  jns     short loc_14007C8E2
0x14007c8d2  xor     r15d, r15d
0x14007c8d5  xor     r12d, r12d
0x14007c8d8  jmp     short loc_14007C8E2
0x14007c8da  mov     r12d, [rsp+98h+arg_8]
0x14007c8e2  mov     rax, ds:0FFFFF78000000014h
0x14007c8ec  mov     ecx, [rsp+98h+arg_0]
0x14007c8f3  mov     [rdi+20h], rax
0x14007c8f7  mov     al, [rsp+98h+arg_10]
0x14007c8fe  mov     [rdi+18h], ecx
0x14007c901  mov     [rdi+1Ch], al
0x14007c904  mov     al, [rsp+98h+arg_18]
0x14007c90b  mov     [rdi+1Dh], al
0x14007c90e  mov     eax, [rsp+98h+arg_20]
0x14007c915  mov     [rdi+3Ch], eax
0x14007c918  mov     rbx, cs:MpData
0x14007c91f  call    cs:__imp_KeEnterCriticalRegion
0x14007c926  nop     dword ptr [rax+rax+00h]
0x14007c92b  mov     dl, 1; Wait
0x14007c92d  lea     rcx, [rbx+2F0h]; Resource
0x14007c934  call    cs:__imp_ExAcquireResourceSharedLite
0x14007c93b  nop     dword ptr [rax+rax+00h]
0x14007c940  mov     rax, cs:MpData
0x14007c947  mov     ecx, [rax+260h]
0x14007c94d  mov     [rdi+40h], ecx
0x14007c950  mov     rax, cs:MpData
0x14007c957  mov     ecx, [rax+264h]
0x14007c95d  mov     [rdi+44h], ecx
0x14007c960  mov     rax, cs:MpData
0x14007c967  mov     ecx, [rax+268h]
0x14007c96d  mov     [rdi+48h], ecx
0x14007c970  mov     rax, cs:MpData
0x14007c977  mov     ecx, [rax+26Ch]
0x14007c97d  mov     [rdi+4Ch], ecx
0x14007c980  mov     rax, cs:MpData
0x14007c987  mov     ecx, [rax+0E0h]
0x14007c98d  mov     [rdi+50h], ecx
0x14007c990  mov     rax, cs:MpData
0x14007c997  mov     ecx, [rax+0DCh]
0x14007c99d  mov     [rdi+54h], ecx
0x14007c9a0  mov     rcx, cs:MpData
0x14007c9a7  add     rcx, 2F0h; Resource
0x14007c9ae  call    cs:__imp_ExReleaseResourceLite
0x14007c9b5  nop     dword ptr [rax+rax+00h]
0x14007c9ba  call    cs:__imp_KeLeaveCriticalRegion
0x14007c9c1  nop     dword ptr [rax+rax+00h]
0x14007c9c6  mov     bl, [rsp+98h+arg_10]
0x14007c9cd  test    bl, bl
0x14007c9cf  jnz     short loc_14007C9DA
0x14007c9d1  cmp     [rsp+98h+arg_18], bl
0x14007c9d8  jz      short loc_14007C9F1
0x14007c9da  mov     rax, [rsp+98h+var_58]
0x14007c9df  mov     [rdi+30h], r13d
0x14007c9e3  mov     [rdi+2Ch], ebp
0x14007c9e6  mov     [rdi+28h], eax
0x14007c9e9  mov     [rdi+38h], r12d
0x14007c9ed  mov     [rdi+34h], r15d
0x14007c9f1  mov     [rdi+8], r14d
0x14007c9f5  lea     rcx, [rdi+18h]
0x14007c9f9  mov     dword ptr [rdi+10h], 0Bh
0x14007ca00  call    MpPersistFilterHealthInformation
0x14007ca05  test    eax, eax
0x14007ca07  jns     short loc_14007CA48
0x14007ca09  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ca10  lea     rbp, WPP_GLOBAL_Control
0x14007ca17  cmp     rcx, rbp
0x14007ca1a  jz      short loc_14007CA4F
0x14007ca1c  mov     ecx, [rcx+2Ch]
0x14007ca1f  test    cl, 2
0x14007ca22  jz      short loc_14007CA4F
0x14007ca24  lfence
0x14007ca27  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ca2e  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14007ca35  mov     edx, 58h ; 'X'
0x14007ca3a  mov     r9d, eax
0x14007ca3d  mov     rcx, [rcx+18h]
0x14007ca41  call    WPP_SF_d
0x14007ca46  jmp     short loc_14007CA4F
0x14007ca48  lea     rbp, WPP_GLOBAL_Control
0x14007ca4f  xor     r8d, r8d
0x14007ca52  mov     [rsp+98h+var_78], 0
0x14007ca5b  test    bl, bl
0x14007ca5d  mov     r9d, 1
0x14007ca63  mov     edx, r14d
0x14007ca66  mov     rcx, rdi
0x14007ca69  setnz   r8b
0x14007ca6d  call    MpAsyncSendNotification
0x14007ca72  mov     ebx, eax
0x14007ca74  test    eax, eax
0x14007ca76  jns     short loc_14007CAB9
0x14007ca78  mov     rax, cs:WPP_GLOBAL_Control
0x14007ca7f  cmp     rax, rbp
0x14007ca82  jz      short loc_14007CAE6
0x14007ca84  mov     eax, [rax+2Ch]
0x14007ca87  test    al, 1
0x14007ca89  jz      short loc_14007CAE6
0x14007ca8b  lfence
0x14007ca8e  mov     r9, gs:188h
0x14007ca97  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14007ca9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007caa5  mov     edx, 59h ; 'Y'
0x14007caaa  mov     dword ptr [rsp+98h+var_78], ebx
0x14007caae  mov     rcx, [rcx+18h]
0x14007cab2  call    WPP_SF_qD
0x14007cab7  jmp     short loc_14007CAE6
0x14007cab9  mov     rdx, cs:MpData
0x14007cac0  xor     eax, eax
0x14007cac2  xchg    eax, [rdx+264h]
0x14007cac8  mov     rdx, cs:MpData
0x14007cacf  xor     eax, eax
0x14007cad1  xchg    eax, [rdx+268h]
0x14007cad7  mov     rdx, cs:MpData
0x14007cade  xor     eax, eax
0x14007cae0  xchg    eax, [rdx+26Ch]
0x14007cae6  mov     rcx, rdi
0x14007cae9  call    MpAsyncDereferenceNotification
0x14007caee  jmp     short loc_14007CB2F
0x14007caf0  mov     rax, cs:WPP_GLOBAL_Control
0x14007caf7  cmp     rax, rdi
0x14007cafa  jz      short loc_14007CB2F
0x14007cafc  mov     eax, [rax+2Ch]
0x14007caff  test    al, 1
0x14007cb01  jz      short loc_14007CB2F
0x14007cb03  lfence
0x14007cb06  mov     r9, gs:188h
0x14007cb0f  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14007cb16  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cb1d  mov     edx, 5Ah ; 'Z'
0x14007cb22  mov     dword ptr [rsp+98h+var_78], ebx
0x14007cb26  mov     rcx, [rcx+18h]
0x14007cb2a  call    WPP_SF_qD
0x14007cb2f  test    rsi, rsi
0x14007cb32  jz      short loc_14007CB3C
0x14007cb34  mov     rcx, rsi
0x14007cb37  call    MpFreeString
0x14007cb3c  mov     eax, ebx
0x14007cb3e  add     rsp, 58h
0x14007cb42  pop     r15
0x14007cb44  pop     r14
0x14007cb46  pop     r13
0x14007cb48  pop     r12
0x14007cb4a  pop     rdi
0x14007cb4b  pop     rsi
0x14007cb4c  pop     rbp
0x14007cb4d  pop     rbx
0x14007cb4e  retn
```
