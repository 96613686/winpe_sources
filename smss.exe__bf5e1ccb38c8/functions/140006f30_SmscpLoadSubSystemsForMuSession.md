# SmscpLoadSubSystemsForMuSession

- ea: `0x140006f30`
- end: `0x1400072da`
- name: `SmscpLoadSubSystemsForMuSession`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006680`

## callees

- `0x1400010ec`
- `0x140003450`
- `0x140006f30`
- `0x14000d418`
- `0x14000d4c0`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x140007098`
- `ntdll!NtSetSystemInformation` at `0x140007098`
- `ntdll!RtlEqualUnicodeString` at `0x140007188`
- `ntdll!RtlEqualUnicodeString` at `0x140007188`
- `ntdll!NtSerializeBoot` at `0x14000702f`
- `ntdll!NtSerializeBoot` at `0x1400071f7`
- `ntdll!RtlAcquirePrivilege` at `0x140006f75`
- `ntdll!RtlAcquirePrivilege` at `0x140006f75`
- `ntdll!RtlReleasePrivilege` at `0x1400070b8`
- `ntdll!RtlReleasePrivilege` at `0x1400070b8`

## pseudocode

```c
__int64 __fastcall SmscpLoadSubSystemsForMuSession(int a1)
{
  unsigned int v1; // esi
  NTSTATUS v3; // eax
  NTSTATUS v4; // ebx
  char v6; // r12
  int v7; // eax
  char *v8; // rcx
  _DWORD *v9; // r15
  char *v10; // r13
  __int64 v11; // rdx
  char *v12; // r8
  unsigned int v13; // esi
  char *v14; // r9
  int v15; // r15d
  BOOLEAN v16; // al
  int v17; // r8d
  int v18; // ecx
  int v19; // eax
  int v20; // ebx
  int v21; // eax
  _DWORD *v22; // rsi
  char *v23; // r15
  int v24; // edi
  signed __int32 v25[8]; // [rsp+0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+20h] [rbp-40h]
  char *v27; // [rsp+30h] [rbp-30h]
  __int64 SystemInformation; // [rsp+38h] [rbp-28h] BYREF
  char *v29; // [rsp+40h] [rbp-20h]
  UNICODE_STRING String1; // [rsp+48h] [rbp-18h] BYREF
  int v31; // [rsp+A8h] [rbp+48h]
  PVOID ReturnedState; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int *v33; // [rsp+B8h] [rbp+58h]

  v1 = 0;
  ReturnedState = 0;
  SystemInformation = 0;
  v29 = 0;
  String1 = 0;
  v3 = RtlAcquirePrivilege((PULONG)&SmpSessionCreatePrivilege, 1u, 2u, &ReturnedState);
  v4 = v3;
  if ( v3 < 0 )
  {
    SmpLogFailure("SmscpLoadSubSystemsForMuSession", 814, (unsigned int)v3);
    *(_DWORD *)SmscpSharedWindow = 1;
    _InterlockedOr(v25, 0);
    *((_DWORD *)SmscpSharedWindow + 2) = 816;
    *((_DWORD *)SmscpSharedWindow + 1) = v4;
LABEL_3:
    *((_QWORD *)SmscpSharedWindow + 2) = SmscpLoadSubSystemsForMuSession;
    return (unsigned int)v4;
  }
  v6 = 0;
  if ( !a1 && SmpSerializeBoot == 1 )
  {
    v7 = SmpNtSerializeBoot();
    v4 = v7;
    if ( v7 >= 0 )
    {
      v6 = 1;
    }
    else
    {
      SmpLogFailure("SmscpLoadSubSystemsForMuSession", 839, (unsigned int)v7);
      *(_DWORD *)SmscpSharedWindow = 1;
      _InterlockedOr(v25, 0);
      *((_DWORD *)SmscpSharedWindow + 2) = 841;
      *((_DWORD *)SmscpSharedWindow + 1) = v4;
      *((_QWORD *)SmscpSharedWindow + 2) = NtSerializeBoot;
    }
  }
  v8 = (char *)SmpMappedView;
  v9 = (char *)SmpMappedView + 64;
  v10 = (char *)SmpMappedView + *((_QWORD *)SmpMappedView + 7);
  if ( *((_DWORD *)SmpMappedView + 16) )
  {
    while ( 1 )
    {
      v11 = 16LL * v1;
      v29 = &v8[*(_QWORD *)&v10[v11]];
      WORD1(SystemInformation) = *(_WORD *)&v10[v11 + 8];
      LOWORD(SystemInformation) = WORD1(SystemInformation);
      v4 = NtSetSystemInformation(SystemExtendServiceTableInformation, &SystemInformation, 0x10u);
      if ( v4 < 0 )
        break;
      if ( ++v1 >= *v9 )
        break;
      v8 = (char *)SmpMappedView;
    }
  }
  RtlReleasePrivilege(ReturnedState);
  if ( v4 < 0 )
  {
    SmpLogFailureString("SmscpLoadSubSystemsForMuSession", 880, v29, (unsigned int)v4);
    *(_DWORD *)SmscpSharedWindow = 1;
    _InterlockedOr(v25, 0);
    *((_DWORD *)SmscpSharedWindow + 2) = 882;
LABEL_16:
    *((_DWORD *)SmscpSharedWindow + 1) = v4;
    goto LABEL_3;
  }
  v12 = (char *)SmpMappedView;
  v13 = 0;
  v14 = (char *)SmpMappedView + *((_QWORD *)SmpMappedView + 9);
  v33 = (unsigned int *)((char *)SmpMappedView + 80);
  v27 = v14;
  if ( *((_DWORD *)SmpMappedView + 20) )
  {
    v15 = 12296;
    if ( a1 )
      v15 = 4104;
    while ( 1 )
    {
      String1.Buffer = (PWSTR)&v12[*(_QWORD *)&v14[16 * v13]];
      String1.MaximumLength = *(_WORD *)&v14[16 * v13 + 8];
      String1.Length = String1.MaximumLength;
      v29 = &v12[*(_QWORD *)&v14[16 * v13 + 16]];
      WORD1(SystemInformation) = *(_WORD *)&v14[16 * v13 + 24];
      LOWORD(SystemInformation) = WORD1(SystemInformation);
      v16 = RtlEqualUnicodeString(&String1, &SmpDebugKeyword, 1u);
      v18 = v15 | 1;
      if ( !v16 )
        v18 = v15;
      v31 = v18;
      if ( !v6 && a1 == 1 && SmpSerializeBoot == 2 )
      {
        v19 = SmpNtSerializeBoot();
        v20 = v19;
        if ( v19 >= 0 )
        {
          v6 = 1;
        }
        else
        {
          SmpLogFailure("SmscpLoadSubSystemsForMuSession", 941, (unsigned int)v19);
          *(_DWORD *)SmscpSharedWindow = 1;
          _InterlockedOr(v25, 0);
          *((_DWORD *)SmscpSharedWindow + 2) = 943;
          *((_DWORD *)SmscpSharedWindow + 1) = v20;
          *((_QWORD *)SmscpSharedWindow + 2) = NtSerializeBoot;
        }
        v18 = v31;
      }
      v21 = SmpExecuteCommand((unsigned int)&SystemInformation, a1, v17, v18, 0);
      v4 = v21;
      if ( v21 < 0 )
        break;
      v13 += 2;
      v12 = (char *)SmpMappedView;
      if ( v13 >= *v33 )
        goto LABEL_33;
      v14 = v27;
    }
    SmpLogFailureString("SmscpLoadSubSystemsForMuSession", 958, String1.Buffer, (unsigned int)v21);
    *(_DWORD *)SmscpSharedWindow = 1;
    _InterlockedOr(v25, 0);
    *((_DWORD *)SmscpSharedWindow + 2) = 960;
    goto LABEL_16;
  }
LABEL_33:
  v22 = v12 + 96;
  v23 = &v12[*((_QWORD *)v12 + 11)];
  v24 = 0;
  if ( *((_DWORD *)v12 + 24) )
  {
    while ( 1 )
    {
      v26 = 0;
      v29 = &v12[*(_QWORD *)&v23[16 * v24]];
      WORD1(SystemInformation) = *(_WORD *)&v23[16 * v24 + 8];
      LOWORD(SystemInformation) = WORD1(SystemInformation);
      SmpExecuteCommand((unsigned int)&SystemInformation, a1, (_DWORD)v12, 0, 0);
      if ( (unsigned int)++v24 >= *v22 )
        break;
      v12 = (char *)SmpMappedView;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140006f30  mov     [rsp-38h+arg_0], rbx
0x140006f35  push    rbp
0x140006f36  push    rsi
0x140006f37  push    rdi
0x140006f38  push    r12
0x140006f3a  push    r13
0x140006f3c  push    r14
0x140006f3e  push    r15
0x140006f40  mov     rbp, rsp
0x140006f43  sub     rsp, 60h
0x140006f47  xor     esi, esi
0x140006f49  lea     r9, [rbp+ReturnedState]; ReturnedState
0x140006f4d  mov     r14d, ecx
0x140006f50  mov     [rbp+ReturnedState], rsi
0x140006f54  xorps   xmm0, xmm0
0x140006f57  mov     [rbp+SystemInformation], rsi
0x140006f5b  lea     rcx, SmpSessionCreatePrivilege; Privilege
0x140006f62  mov     [rbp+var_20], rsi
0x140006f66  lea     r15d, [rsi+1]
0x140006f6a  mov     edx, r15d; NumPriv
0x140006f6d  lea     r8d, [rsi+2]; Flags
0x140006f71  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140006f75  call    cs:__imp_RtlAcquirePrivilege
0x140006f7b  mov     ebx, eax
0x140006f7d  test    eax, eax
0x140006f7f  jns     short loc_140006FE7
0x140006f81  mov     r8d, eax
0x140006f84  lea     rcx, aSmscploadsubsy_0; "SmscpLoadSubSystemsForMuSession"
0x140006f8b  mov     edx, 32Eh
0x140006f90  call    SmpLogFailure
0x140006f95  mov     rcx, cs:SmscpSharedWindow
0x140006f9c  mov     [rcx], r15d
0x140006f9f  lock or [rsp+60h+var_60], esi
0x140006fa3  mov     rcx, cs:SmscpSharedWindow
0x140006faa  mov     dword ptr [rcx+8], 330h
0x140006fb1  mov     rcx, cs:SmscpSharedWindow
0x140006fb8  mov     [rcx+4], ebx
0x140006fbb  mov     rax, cs:SmscpSharedWindow
0x140006fc2  lea     rcx, SmscpLoadSubSystemsForMuSession
0x140006fc9  mov     [rax+10h], rcx
0x140006fcd  mov     eax, ebx
0x140006fcf  mov     rbx, [rsp+60h+arg_0]
0x140006fd7  add     rsp, 60h
0x140006fdb  pop     r15
0x140006fdd  pop     r14
0x140006fdf  pop     r13
0x140006fe1  pop     r12
0x140006fe3  pop     rdi
0x140006fe4  pop     rsi
0x140006fe5  pop     rbp
0x140006fe6  retn
0x140006fe7  lea     rdi, aSmscploadsubsy_0; "SmscpLoadSubSystemsForMuSession"
0x140006fee  mov     r12b, sil
0x140006ff1  test    r14d, r14d
0x140006ff4  jnz     short loc_140007057
0x140006ff6  cmp     cs:SmpSerializeBoot, r15d
0x140006ffd  jnz     short loc_140007057
0x140006fff  call    SmpNtSerializeBoot
0x140007004  mov     ebx, eax
0x140007006  test    eax, eax
0x140007008  jns     short loc_140007054
0x14000700a  mov     r8d, eax
0x14000700d  mov     edx, 347h
0x140007012  mov     rcx, rdi
0x140007015  call    SmpLogFailure
0x14000701a  mov     rax, cs:SmscpSharedWindow
0x140007021  mov     [rax], r15d
0x140007024  lock or [rsp+60h+var_60], esi
0x140007028  mov     rax, cs:SmscpSharedWindow
0x14000702f  mov     rcx, cs:__imp_NtSerializeBoot
0x140007036  mov     dword ptr [rax+8], 349h
0x14000703d  mov     rax, cs:SmscpSharedWindow
0x140007044  mov     [rax+4], ebx
0x140007047  mov     rax, cs:SmscpSharedWindow
0x14000704e  mov     [rax+10h], rcx
0x140007052  jmp     short loc_140007057
0x140007054  mov     r12b, r15b
0x140007057  mov     rcx, cs:SmpMappedView
0x14000705e  mov     r13, [rcx+38h]
0x140007062  lea     r15, [rcx+40h]
0x140007066  add     r13, rcx
0x140007069  cmp     [r15], esi
0x14000706c  jbe     short loc_1400070B4
0x14000706e  mov     r8d, 10h; SystemInformationLength
0x140007074  mov     edx, esi
0x140007076  shl     rdx, 4
0x14000707a  add     rcx, [rdx+r13]
0x14000707e  mov     [rbp+var_20], rcx
0x140007082  lea     ecx, [r8+16h]; SystemInformationClass
0x140007086  movzx   eax, word ptr [rdx+r13+8]
0x14000708c  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x140007090  mov     word ptr [rbp+SystemInformation+2], ax
0x140007094  mov     word ptr [rbp+SystemInformation], ax
0x140007098  call    cs:__imp_NtSetSystemInformation
0x14000709e  mov     ebx, eax
0x1400070a0  test    eax, eax
0x1400070a2  js      short loc_1400070B4
0x1400070a4  inc     esi
0x1400070a6  cmp     esi, [r15]
0x1400070a9  jnb     short loc_1400070B4
0x1400070ab  mov     rcx, cs:SmpMappedView
0x1400070b2  jmp     short loc_14000706E
0x1400070b4  mov     rcx, [rbp+ReturnedState]; ReturnedState
0x1400070b8  call    cs:__imp_RtlReleasePrivilege
0x1400070be  test    ebx, ebx
0x1400070c0  jns     short loc_140007105
0x1400070c2  mov     r8, [rbp+var_20]
0x1400070c6  mov     r9d, ebx
0x1400070c9  mov     edx, 370h
0x1400070ce  mov     rcx, rdi
0x1400070d1  call    SmpLogFailureString
0x1400070d6  mov     rax, cs:SmscpSharedWindow
0x1400070dd  mov     dword ptr [rax], 1
0x1400070e3  lock or [rsp+60h+var_60], 0
0x1400070e8  mov     rax, cs:SmscpSharedWindow
0x1400070ef  mov     dword ptr [rax+8], 372h
0x1400070f6  mov     rax, cs:SmscpSharedWindow
0x1400070fd  mov     [rax+4], ebx
0x140007100  jmp     loc_140006FBB
0x140007105  mov     r8, cs:SmpMappedView
0x14000710c  xor     esi, esi
0x14000710e  mov     r9, [r8+48h]
0x140007112  lea     rax, [r8+50h]
0x140007116  add     r9, r8
0x140007119  mov     [rbp+arg_18], rax
0x14000711d  mov     [rbp+var_30], r9
0x140007121  cmp     [rax], esi
0x140007123  jbe     loc_14000727C
0x140007129  test    r14d, r14d
0x14000712c  mov     eax, 1008h
0x140007131  mov     r15d, 3008h
0x140007137  cmovnz  r15d, eax
0x14000713b  mov     r13d, r15d
0x14000713e  or      r13d, 1
0x140007142  mov     edx, esi
0x140007144  add     rdx, rdx
0x140007147  mov     rcx, [r9+rdx*8]
0x14000714b  add     rcx, r8
0x14000714e  mov     [rbp+String1.Buffer], rcx
0x140007152  movzx   eax, word ptr [r9+rdx*8+8]
0x140007158  mov     [rbp+String1.MaximumLength], ax
0x14000715c  mov     [rbp+String1.Length], ax
0x140007160  mov     rcx, [r9+rdx*8+10h]
0x140007165  add     rcx, r8
0x140007168  mov     r8b, 1; CaseInSensitive
0x14000716b  mov     [rbp+var_20], rcx
0x14000716f  lea     rcx, [rbp+String1]; String1
0x140007173  movzx   eax, word ptr [r9+rdx*8+18h]
0x140007179  lea     rdx, SmpDebugKeyword; String2
0x140007180  mov     word ptr [rbp+SystemInformation+2], ax
0x140007184  mov     word ptr [rbp+SystemInformation], ax
0x140007188  call    cs:__imp_RtlEqualUnicodeString
0x14000718e  test    al, al
0x140007190  mov     ecx, r13d
0x140007193  cmovz   ecx, r15d
0x140007197  mov     [rbp+arg_8], ecx
0x14000719a  test    r12b, r12b
0x14000719d  jnz     short loc_14000720A
0x14000719f  cmp     r14d, 1
0x1400071a3  jnz     short loc_14000720A
0x1400071a5  cmp     cs:SmpSerializeBoot, 2
0x1400071ac  jnz     short loc_14000720A
0x1400071ae  call    SmpNtSerializeBoot
0x1400071b3  mov     ebx, eax
0x1400071b5  test    eax, eax
0x1400071b7  jns     short loc_140007204
0x1400071b9  mov     r8d, eax
0x1400071bc  mov     edx, 3ADh
0x1400071c1  mov     rcx, rdi
0x1400071c4  call    SmpLogFailure
0x1400071c9  mov     rcx, cs:SmscpSharedWindow
0x1400071d0  mov     [rcx], r14d
0x1400071d3  lock or [rsp+60h+var_60], 0
0x1400071d8  mov     rcx, cs:SmscpSharedWindow
0x1400071df  mov     dword ptr [rcx+8], 3AFh
0x1400071e6  mov     rcx, cs:SmscpSharedWindow
0x1400071ed  mov     [rcx+4], ebx
0x1400071f0  mov     rax, cs:SmscpSharedWindow
0x1400071f7  mov     rcx, cs:__imp_NtSerializeBoot
0x1400071fe  mov     [rax+10h], rcx
0x140007202  jmp     short loc_140007207
0x140007204  mov     r12b, 1
0x140007207  mov     ecx, [rbp+arg_8]
0x14000720a  mov     r9d, ecx
0x14000720d  mov     [rsp+60h+var_40], 0
0x140007216  lea     rcx, [rbp+SystemInformation]
0x14000721a  mov     edx, r14d
0x14000721d  call    SmpExecuteCommand
0x140007222  mov     ebx, eax
0x140007224  test    eax, eax
0x140007226  js      short loc_140007243
0x140007228  mov     rax, [rbp+arg_18]
0x14000722c  add     esi, 2
0x14000722f  mov     r8, cs:SmpMappedView
0x140007236  cmp     esi, [rax]
0x140007238  jnb     short loc_14000727C
0x14000723a  mov     r9, [rbp+var_30]
0x14000723e  jmp     loc_140007142
0x140007243  mov     r8, [rbp+String1.Buffer]
0x140007247  mov     r9d, ebx
0x14000724a  mov     edx, 3BEh
0x14000724f  mov     rcx, rdi
0x140007252  call    SmpLogFailureString
0x140007257  mov     rax, cs:SmscpSharedWindow
0x14000725e  mov     dword ptr [rax], 1
0x140007264  lock or [rsp+60h+var_60], 0
0x140007269  mov     rax, cs:SmscpSharedWindow
0x140007270  mov     dword ptr [rax+8], 3C0h
0x140007277  jmp     loc_1400070F6
0x14000727c  mov     r15, [r8+58h]
0x140007280  lea     rsi, [r8+60h]
0x140007284  add     r15, r8
0x140007287  xor     edi, edi
0x140007289  cmp     [rsi], edi
0x14000728b  jbe     loc_140006FCD
0x140007291  mov     edx, edi
0x140007293  xor     r9d, r9d
0x140007296  add     rdx, rdx
0x140007299  mov     [rsp+60h+var_40], 0
0x1400072a2  mov     rcx, [r15+rdx*8]
0x1400072a6  add     rcx, r8
0x1400072a9  mov     [rbp+var_20], rcx
0x1400072ad  lea     rcx, [rbp+SystemInformation]
0x1400072b1  movzx   eax, word ptr [r15+rdx*8+8]
0x1400072b7  mov     edx, r14d
0x1400072ba  mov     word ptr [rbp+SystemInformation+2], ax
0x1400072be  mov     word ptr [rbp+SystemInformation], ax
0x1400072c2  call    SmpExecuteCommand
0x1400072c7  inc     edi
0x1400072c9  cmp     edi, [rsi]
0x1400072cb  jnb     loc_140006FCD
0x1400072d1  mov     r8, cs:SmpMappedView
0x1400072d8  jmp     short loc_140007291
```
