# MpSetProcessHardening

- ea: `0x140037928`
- end: `0x140037cfc`
- name: `MpSetProcessHardening`
- size: `980`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x140036780`
- `0x140093bf8`

## callees

- `0x1400051bc`
- `0x140005944`
- `0x1400118d0`
- `0x140037928`
- `0x14006bfb0`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x140037c35`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140037c35`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400379f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037a2e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037a64`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037a9a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037ad0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037b06`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400379f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037a2e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037a64`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037a9a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037ad0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037b06`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400379aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400379e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037a17`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037a4d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037a83`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037ab9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037aef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400379aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400379e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037a17`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037a4d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037a83`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037ab9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037aef`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140037cd4`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140037cd4`
- `ntoskrnl!KeBugCheck` at `0x140037cef`
- `ntoskrnl!KeBugCheck` at `0x140037cef`
- `ntoskrnl!ObfDereferenceObject` at `0x140037c9c`
- `ntoskrnl!ObfDereferenceObject` at `0x140037c9c`
- `FLTMGR!FltParseFileName` at `0x1400379c2`
- `FLTMGR!FltParseFileName` at `0x1400379c2`

## string_xrefs

- `0x140037a42`: `mpcopyaccelerator.exe`
- `0x140037a78`: `mpdefendercoreservice.exe`
- `0x140037aae`: `MpDlpService.exe`

## pseudocode

```c
char __fastcall MpSetProcessHardening(PEPROCESS Process, __int64 a2, const UNICODE_STRING *a3)
{
  signed __int64 v3; // rax
  __int64 v7; // rdx
  void *v8; // rbx
  int v9; // ecx
  int v11; // [rsp+20h] [rbp-40h]
  PEPROCESS Processa; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING String2; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF

  LOBYTE(v3) = MpData;
  Processa = 0;
  DestinationString = 0;
  String2 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 1) == 0 )
    return v3;
  if ( !a2 || !a3 || !a3->Length )
    goto LABEL_13;
  RtlInitUnicodeString(&DestinationString, &word_140012D30);
  LODWORD(v3) = FltParseFileName(a3, 0, 0, &DestinationString);
  if ( (int)v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_13;
      v7 = 29;
      v11 = v3;
LABEL_25:
      _mm_lfence();
      LOBYTE(v3) = WPP_SF_qD(
                     WPP_GLOBAL_Control->AttachedDevice,
                     v7,
                     WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
                     KeGetCurrentThread(),
                     v11);
      goto LABEL_13;
    }
  }
  else
  {
    RtlInitUnicodeString(&String2, L"mpcmdrun.exe");
    if ( RtlEqualUnicodeString(&DestinationString, &String2, 1u)
      || (RtlInitUnicodeString(&String2, L"msmpeng.exe"), RtlEqualUnicodeString(&DestinationString, &String2, 1u))
      || (RtlInitUnicodeString(&String2, L"mpcopyaccelerator.exe"),
          RtlEqualUnicodeString(&DestinationString, &String2, 1u)) )
    {
      LOBYTE(v3) = MpData;
      v8 = *(void **)(MpData + 2376);
    }
    else
    {
      RtlInitUnicodeString(&String2, L"mpdefendercoreservice.exe");
      if ( RtlEqualUnicodeString(&DestinationString, &String2, 1u) )
      {
        LOBYTE(v3) = MpData;
        v8 = *(void **)(MpData + 2416);
      }
      else
      {
        RtlInitUnicodeString(&String2, L"MpDlpService.exe");
        if ( RtlEqualUnicodeString(&DestinationString, &String2, 1u) )
        {
          LOBYTE(v3) = MpData;
          v8 = *(void **)(MpData + 2392);
        }
        else
        {
          RtlInitUnicodeString(&String2, L"nissrv.exe");
          LOBYTE(v3) = RtlEqualUnicodeString(&DestinationString, &String2, 1u);
          if ( !(_BYTE)v3 )
            goto LABEL_12;
          LODWORD(v3) = *(_DWORD *)(MpData + 864);
          if ( (v3 & 8) == 0 )
            goto LABEL_12;
          v8 = *(void **)(MpData + 2384);
        }
      }
    }
    if ( Process )
    {
LABEL_19:
      if ( v8 )
      {
        LOBYTE(v3) = MpMatchPerServiceSidByObj(Process, v8);
        if ( (_BYTE)v3 )
        {
          _InterlockedOr((volatile signed __int32 *)(a2 + 52), 0x10u);
          goto LABEL_13;
        }
      }
LABEL_12:
      _InterlockedAnd((volatile signed __int32 *)(a2 + 52), 0xFFFFFFEF);
LABEL_13:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        LODWORD(v3) = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (v3 & 4) != 0 )
          LOBYTE(v3) = WPP_SF_Zd(
                         WPP_GLOBAL_Control->AttachedDevice,
                         31,
                         (unsigned int)WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
                         (_DWORD)a3,
                         *(_DWORD *)(a2 + 52));
      }
      goto LABEL_16;
    }
    LODWORD(v3) = PsLookupProcessByProcessId(*(HANDLE *)(a2 + 24), &Processa);
    v9 = v3;
    if ( (int)v3 >= 0 )
    {
      _InterlockedIncrement64(&ObTotalReferences);
      Process = Processa;
      goto LABEL_19;
    }
    LOBYTE(v3) = (_BYTE)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v3) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (v3 & 1) == 0 )
        goto LABEL_13;
      v7 = 30;
      v11 = v9;
      goto LABEL_25;
    }
  }
LABEL_16:
  if ( Processa )
  {
    ObfDereferenceObject(Processa);
    v3 = _InterlockedExchangeAdd64(&ObTotalReferences, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v3 - 1 < 0 )
    {
      LOBYTE(v3) = MpData;
      if ( *(int *)(MpData + 868) < 0 )
      {
        LOBYTE(v3) = KdRefreshDebuggerNotPresent();
        if ( (_BYTE)v3 )
          KeBugCheck(1u);
        __debugbreak();
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140037928  push    rbp
0x14003792a  push    rbx
0x14003792b  push    rsi
0x14003792c  push    rdi
0x14003792d  push    r12
0x14003792f  push    r14
0x140037931  push    r15
0x140037933  mov     rbp, rsp
0x140037936  sub     rsp, 60h
0x14003793a  mov     rax, cs:__security_cookie
0x140037941  xor     rax, rsp
0x140037944  mov     [rbp+var_8], rax
0x140037948  mov     rax, cs:MpData
0x14003794f  xor     r15d, r15d
0x140037952  xorps   xmm0, xmm0
0x140037955  mov     [rbp+Process], r15
0x140037959  xorps   xmm1, xmm1
0x14003795c  mov     rsi, rcx
0x14003795f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140037963  mov     r14, r8
0x140037966  mov     rdi, rdx
0x140037969  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14003796d  mov     ecx, [rax+360h]
0x140037973  test    cl, 1
0x140037976  jz      loc_140037B43
0x14003797c  lea     r12, WPP_GLOBAL_Control
0x140037983  test    rdx, rdx
0x140037986  jz      loc_140037B1F
0x14003798c  test    r8, r8
0x14003798f  jz      loc_140037B1F
0x140037995  cmp     [r8], r15w
0x140037999  jz      loc_140037B1F
0x14003799f  lea     rdx, word_140012D30; SourceString
0x1400379a6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400379aa  call    cs:__imp_RtlInitUnicodeString
0x1400379b1  nop     dword ptr [rax+rax+00h]
0x1400379b6  lea     r9, [rbp+DestinationString]; FinalComponent
0x1400379ba  xor     r8d, r8d; Stream
0x1400379bd  xor     edx, edx; Extension
0x1400379bf  mov     rcx, r14; FileName
0x1400379c2  call    cs:__imp_FltParseFileName
0x1400379c9  nop     dword ptr [rax+rax+00h]
0x1400379ce  test    eax, eax
0x1400379d0  js      loc_140037B83
0x1400379d6  lea     rdx, aMpcmdrunExe; "mpcmdrun.exe"
0x1400379dd  lea     rcx, [rbp+String2]; DestinationString
0x1400379e1  call    cs:__imp_RtlInitUnicodeString
0x1400379e8  nop     dword ptr [rax+rax+00h]
0x1400379ed  mov     r8b, 1; CaseInSensitive
0x1400379f0  lea     rdx, [rbp+String2]; String2
0x1400379f4  lea     rcx, [rbp+DestinationString]; String1
0x1400379f8  call    cs:__imp_RtlEqualUnicodeString
0x1400379ff  nop     dword ptr [rax+rax+00h]
0x140037a04  test    al, al
0x140037a06  jnz     loc_140037BD3
0x140037a0c  lea     rdx, aMsmpengExe; "msmpeng.exe"
0x140037a13  lea     rcx, [rbp+String2]; DestinationString
0x140037a17  call    cs:__imp_RtlInitUnicodeString
0x140037a1e  nop     dword ptr [rax+rax+00h]
0x140037a23  mov     r8b, 1; CaseInSensitive
0x140037a26  lea     rdx, [rbp+String2]; String2
0x140037a2a  lea     rcx, [rbp+DestinationString]; String1
0x140037a2e  call    cs:__imp_RtlEqualUnicodeString
0x140037a35  nop     dword ptr [rax+rax+00h]
0x140037a3a  test    al, al
0x140037a3c  jnz     loc_140037BD3
0x140037a42  lea     rdx, aMpcopyaccelera; "mpcopyaccelerator.exe"
0x140037a49  lea     rcx, [rbp+String2]; DestinationString
0x140037a4d  call    cs:__imp_RtlInitUnicodeString
0x140037a54  nop     dword ptr [rax+rax+00h]
0x140037a59  mov     r8b, 1; CaseInSensitive
0x140037a5c  lea     rdx, [rbp+String2]; String2
0x140037a60  lea     rcx, [rbp+DestinationString]; String1
0x140037a64  call    cs:__imp_RtlEqualUnicodeString
0x140037a6b  nop     dword ptr [rax+rax+00h]
0x140037a70  test    al, al
0x140037a72  jnz     loc_140037BD3
0x140037a78  lea     rdx, aMpdefendercore; "mpdefendercoreservice.exe"
0x140037a7f  lea     rcx, [rbp+String2]; DestinationString
0x140037a83  call    cs:__imp_RtlInitUnicodeString
0x140037a8a  nop     dword ptr [rax+rax+00h]
0x140037a8f  mov     r8b, 1; CaseInSensitive
0x140037a92  lea     rdx, [rbp+String2]; String2
0x140037a96  lea     rcx, [rbp+DestinationString]; String1
0x140037a9a  call    cs:__imp_RtlEqualUnicodeString
0x140037aa1  nop     dword ptr [rax+rax+00h]
0x140037aa6  test    al, al
0x140037aa8  jnz     loc_140037BE6
0x140037aae  lea     rdx, aMpdlpserviceEx; "MpDlpService.exe"
0x140037ab5  lea     rcx, [rbp+String2]; DestinationString
0x140037ab9  call    cs:__imp_RtlInitUnicodeString
0x140037ac0  nop     dword ptr [rax+rax+00h]
0x140037ac5  mov     r8b, 1; CaseInSensitive
0x140037ac8  lea     rdx, [rbp+String2]; String2
0x140037acc  lea     rcx, [rbp+DestinationString]; String1
0x140037ad0  call    cs:__imp_RtlEqualUnicodeString
0x140037ad7  nop     dword ptr [rax+rax+00h]
0x140037adc  test    al, al
0x140037ade  jnz     loc_140037BF9
0x140037ae4  lea     rdx, aNissrvExe; "nissrv.exe"
0x140037aeb  lea     rcx, [rbp+String2]; DestinationString
0x140037aef  call    cs:__imp_RtlInitUnicodeString
0x140037af6  nop     dword ptr [rax+rax+00h]
0x140037afb  mov     r8b, 1; CaseInSensitive
0x140037afe  lea     rdx, [rbp+String2]; String2
0x140037b02  lea     rcx, [rbp+DestinationString]; String1
0x140037b06  call    cs:__imp_RtlEqualUnicodeString
0x140037b0d  nop     dword ptr [rax+rax+00h]
0x140037b12  test    al, al
0x140037b14  jnz     loc_140037C0C
0x140037b1a  lock and dword ptr [rdi+34h], 0FFFFFFEFh
0x140037b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b26  cmp     rcx, r12
0x140037b29  jz      short loc_140037B36
0x140037b2b  mov     eax, [rcx+2Ch]
0x140037b2e  test    al, 4
0x140037b30  jnz     loc_140037C78
0x140037b36  mov     rcx, [rbp+Process]; Object
0x140037b3a  test    rcx, rcx
0x140037b3d  jnz     loc_140037C9C
0x140037b43  mov     rcx, [rbp+var_8]
0x140037b47  xor     rcx, rsp; StackCookie
0x140037b4a  call    __security_check_cookie
0x140037b4f  add     rsp, 60h
0x140037b53  pop     r15
0x140037b55  pop     r14
0x140037b57  pop     r12
0x140037b59  pop     rdi
0x140037b5a  pop     rsi
0x140037b5b  pop     rbx
0x140037b5c  pop     rbp
0x140037b5d  retn
0x140037b5f  test    rsi, rsi
0x140037b62  jz      loc_140037C2D
0x140037b68  test    rbx, rbx
0x140037b6b  jz      short loc_140037B1A
0x140037b6d  mov     rdx, rbx; Sid
0x140037b70  mov     rcx, rsi; Process
0x140037b73  call    MpMatchPerServiceSidByObj
0x140037b78  test    al, al
0x140037b7a  jz      short loc_140037B1A
0x140037b7c  lock or dword ptr [rdi+34h], 10h
0x140037b81  jmp     short loc_140037B1F
0x140037b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b8a  cmp     rcx, r12
0x140037b8d  jz      short loc_140037B36
0x140037b8f  mov     ecx, [rcx+2Ch]
0x140037b92  test    cl, 1
0x140037b95  jz      short loc_140037B1F
0x140037b97  mov     edx, 1Dh
0x140037b9c  mov     [rsp+60h+var_40], eax
0x140037ba0  jmp     short loc_140037BAB
0x140037ba2  mov     edx, 1Eh
0x140037ba7  mov     [rsp+60h+var_40], ecx
0x140037bab  lfence
0x140037bae  mov     r9, gs:188h
0x140037bb7  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x140037bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140037bc5  mov     rcx, [rcx+18h]
0x140037bc9  call    WPP_SF_qD
0x140037bce  jmp     loc_140037B1F
0x140037bd3  mov     rax, cs:MpData
0x140037bda  mov     rbx, [rax+948h]
0x140037be1  jmp     loc_140037B5F
0x140037be6  mov     rax, cs:MpData
0x140037bed  mov     rbx, [rax+970h]
0x140037bf4  jmp     loc_140037B5F
0x140037bf9  mov     rax, cs:MpData
0x140037c00  mov     rbx, [rax+958h]
0x140037c07  jmp     loc_140037B5F
0x140037c0c  mov     rbx, cs:MpData
0x140037c13  mov     eax, [rbx+360h]
0x140037c19  test    al, 8
0x140037c1b  jz      loc_140037B1A
0x140037c21  mov     rbx, [rbx+950h]
0x140037c28  jmp     loc_140037B5F
0x140037c2d  mov     rcx, [rdi+18h]; ProcessId
0x140037c31  lea     rdx, [rbp+Process]; Process
0x140037c35  call    cs:__imp_PsLookupProcessByProcessId
0x140037c3c  nop     dword ptr [rax+rax+00h]
0x140037c41  mov     ecx, eax
0x140037c43  test    eax, eax
0x140037c45  js      short loc_140037C58
0x140037c47  lock inc cs:ObTotalReferences
0x140037c4f  mov     rsi, [rbp+Process]
0x140037c53  jmp     loc_140037B68
0x140037c58  mov     rax, cs:WPP_GLOBAL_Control
0x140037c5f  cmp     rax, r12
0x140037c62  jz      loc_140037B36
0x140037c68  mov     eax, [rax+2Ch]
0x140037c6b  test    al, 1
0x140037c6d  jz      loc_140037B1F
0x140037c73  jmp     loc_140037BA2
0x140037c78  mov     eax, [rdi+34h]
0x140037c7b  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x140037c82  mov     rcx, [rcx+18h]
0x140037c86  mov     edx, 1Fh
0x140037c8b  mov     r9, r14
0x140037c8e  mov     [rsp+60h+var_40], eax
0x140037c92  call    WPP_SF_Zd
0x140037c97  jmp     loc_140037B36
0x140037c9c  call    cs:__imp_ObfDereferenceObject
0x140037ca3  nop     dword ptr [rax+rax+00h]
0x140037ca8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140037cac  lock xadd cs:ObTotalReferences, rax
0x140037cb5  cmp     rax, 1
0x140037cb9  jns     loc_140037B43
0x140037cbf  mov     rax, cs:MpData
0x140037cc6  mov     ecx, [rax+364h]
0x140037ccc  test    ecx, ecx
0x140037cce  jns     loc_140037B43
0x140037cd4  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140037cdb  nop     dword ptr [rax+rax+00h]
0x140037ce0  test    al, al
0x140037ce2  jnz     short loc_140037CEA
0x140037ce4  int     3; Trap to Debugger
0x140037ce5  jmp     loc_140037B43
0x140037cea  mov     ecx, 1; BugCheckCode
0x140037cef  call    cs:__imp_KeBugCheck
```
