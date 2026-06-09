# SqosPostCreate

- ea: `0x140014420`
- end: `0x140014682`
- name: `SqosPostCreate`
- size: `610`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000666c`
- `0x140008250`
- `0x140008368`
- `0x140008880`
- `0x140008d20`
- `0x140014420`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x14001456d`
- `FLTMGR!FltQueryInformationFile` at `0x14001456d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014651`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014651`
- `FLTMGR!FltGetFileNameInformation` at `0x1400145cc`
- `FLTMGR!FltGetFileNameInformation` at `0x1400145cc`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400144ac`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400144ac`
- `FLTMGR!FltReleaseContext` at `0x1400144d9`
- `FLTMGR!FltReleaseContext` at `0x1400144d9`

## string_xrefs

- `0x140014632`: `Created`

## pseudocode

```c
__int64 __fastcall SqosPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, char a4)
{
  NTSTATUS v8; // eax
  __int64 v9; // r8
  UNICODE_STRING *p_Name; // r9
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-68h] BYREF
  _OWORD FileInformation[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v14; // [rsp+78h] [rbp-40h]

  memset(FileInformation, 0, sizeof(FileInformation));
  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, a3, *(_QWORD *)(a2 + 32));
  }
  if ( (a4 & 1) == 0 && CallbackData->IoStatus.Status >= 0 )
  {
    if ( !*(_BYTE *)(a3 + 32)
      && (FltQueryInformationFile(
            *(PFLT_INSTANCE *)(a2 + 24),
            *(PFILE_OBJECT *)(a2 + 32),
            FileInformation,
            0x28u,
            FileBasicInformation,
            0) < 0
       || (v14 & 0x400000) != 0) )
    {
      *(_BYTE *)(a3 + 32) = 1;
    }
    v8 = FltSetStreamHandleContext(
           *(PFLT_INSTANCE *)(a2 + 24),
           *(PFILE_OBJECT *)(a2 + 32),
           FLT_SET_CONTEXT_KEEP_IF_EXISTS,
           (PFLT_CONTEXT)a3,
           0);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids,
          (unsigned int)v8);
      }
    }
    else
    {
      FileNameInformation = 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        FltGetFileNameInformation(CallbackData, 0x401u, &FileNameInformation);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          p_Name = (UNICODE_STRING *)&NAME_NOT_AVAILABLE;
          if ( FileNameInformation )
            p_Name = &FileNameInformation->Name;
          WPP_SF_sqZ_guid_DD(
            WPP_GLOBAL_Control->AttachedDevice,
            *(unsigned __int8 *)(a3 + 32),
            *(unsigned __int8 *)(*(_QWORD *)(a3 + 16) + 124LL),
            (unsigned int)"Created",
            *(_QWORD *)(a2 + 32),
            (__int64)p_Name,
            *(_QWORD *)(a3 + 16) + 88LL,
            *(_BYTE *)(*(_QWORD *)(a3 + 16) + 124LL),
            *(_BYTE *)(a3 + 32));
        }
        if ( FileNameInformation )
          FltReleaseFileNameInformation(FileNameInformation);
      }
    }
  }
  FltReleaseContext((PFLT_CONTEXT)a3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 30, v9, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140014420  push    rbx
0x140014422  push    rbp
0x140014423  push    rsi
0x140014424  push    rdi
0x140014425  push    r14
0x140014427  sub     rsp, 90h
0x14001442e  mov     rax, cs:__security_cookie
0x140014435  xor     rax, rsp
0x140014438  mov     [rsp+0B8h+var_38], rax
0x140014440  xorps   xmm0, xmm0
0x140014443  xor     eax, eax
0x140014445  movups  [rsp+0B8h+FileInformation], xmm0
0x14001444a  mov     [rsp+0B8h+var_40], rax
0x14001444f  mov     edi, r9d
0x140014452  movups  [rsp+0B8h+var_50], xmm0
0x140014457  mov     rbx, r8
0x14001445a  mov     rbp, rdx
0x14001445d  mov     rsi, rcx
0x140014460  mov     rcx, cs:WPP_GLOBAL_Control
0x140014467  lea     r14, WPP_GLOBAL_Control
0x14001446e  cmp     rcx, r14
0x140014471  jz      short loc_14001447E
0x140014473  mov     eax, [rcx+2Ch]
0x140014476  test    al, 2
0x140014478  jnz     loc_140014594
0x14001447e  test    dil, 1
0x140014482  jnz     short loc_1400144D6
0x140014484  cmp     dword ptr [rsi+18h], 0
0x140014488  jl      short loc_1400144D6
0x14001448a  xor     edi, edi
0x14001448c  cmp     [rbx+20h], dil
0x140014490  jz      loc_14001454D
0x140014496  mov     rdx, [rbp+20h]; FileObject
0x14001449a  mov     r9, rbx; NewContext
0x14001449d  mov     rcx, [rbp+18h]; Instance
0x1400144a1  mov     r8d, 1; Operation
0x1400144a7  mov     [rsp+0B8h+OldContext], rdi; OldContext
0x1400144ac  call    cs:__imp_FltSetStreamHandleContext
0x1400144b3  nop     dword ptr [rax+rax+00h]
0x1400144b8  mov     r9d, eax
0x1400144bb  test    eax, eax
0x1400144bd  js      short loc_14001451D
0x1400144bf  mov     rdx, cs:WPP_GLOBAL_Control
0x1400144c6  mov     [rsp+0B8h+FileNameInformation], rdi
0x1400144cb  mov     eax, [rdx+2Ch]
0x1400144ce  test    al, 10h
0x1400144d0  jnz     loc_1400145B5
0x1400144d6  mov     rcx, rbx; Context
0x1400144d9  call    cs:__imp_FltReleaseContext
0x1400144e0  nop     dword ptr [rax+rax+00h]
0x1400144e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144ec  cmp     rcx, r14
0x1400144ef  jz      short loc_1400144FC
0x1400144f1  mov     eax, [rcx+2Ch]
0x1400144f4  test    al, 2
0x1400144f6  jnz     loc_140014662
0x1400144fc  xor     eax, eax
0x1400144fe  mov     rcx, [rsp+0B8h+var_38]
0x140014506  xor     rcx, rsp; StackCookie
0x140014509  call    __security_check_cookie
0x14001450e  add     rsp, 90h
0x140014515  pop     r14
0x140014517  pop     rdi
0x140014518  pop     rsi
0x140014519  pop     rbp
0x14001451a  pop     rbx
0x14001451b  retn
0x14001451d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014524  cmp     rcx, r14
0x140014527  jz      short loc_1400144D6
0x140014529  mov     eax, [rcx+2Ch]
0x14001452c  test    al, 10h
0x14001452e  jz      short loc_1400144D6
0x140014530  cmp     byte ptr [rcx+29h], 2
0x140014534  jb      short loc_1400144D6
0x140014536  mov     rcx, [rcx+18h]
0x14001453a  lea     r8, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids
0x140014541  mov     edx, 1Dh
0x140014546  call    WPP_SF_d
0x14001454b  jmp     short loc_1400144D6
0x14001454d  mov     rdx, [rbp+20h]; FileObject
0x140014551  lea     r8, [rsp+0B8h+FileInformation]; FileInformation
0x140014556  mov     rcx, [rbp+18h]; Instance
0x14001455a  mov     r9d, 28h ; '('; Length
0x140014560  mov     [rsp+0B8h+LengthReturned], rdi; LengthReturned
0x140014565  mov     dword ptr [rsp+0B8h+OldContext], 4; FileInformationClass
0x14001456d  call    cs:__imp_FltQueryInformationFile
0x140014574  nop     dword ptr [rax+rax+00h]
0x140014579  test    eax, eax
0x14001457b  js      short loc_14001458B
0x14001457d  test    dword ptr [rsp+0B8h+var_40], 400000h
0x140014585  jz      loc_140014496
0x14001458b  mov     byte ptr [rbx+20h], 1
0x14001458f  jmp     loc_140014496
0x140014594  cmp     byte ptr [rcx+29h], 5
0x140014598  jb      loc_14001447E
0x14001459e  mov     r9, [rbp+20h]
0x1400145a2  mov     edx, 1Ch
0x1400145a7  mov     rcx, [rcx+18h]
0x1400145ab  call    WPP_SF_q
0x1400145b0  jmp     loc_14001447E
0x1400145b5  cmp     byte ptr [rdx+29h], 4
0x1400145b9  jb      loc_1400144D6
0x1400145bf  lea     r8, [rsp+0B8h+FileNameInformation]; FileNameInformation
0x1400145c4  mov     edx, 401h; NameOptions
0x1400145c9  mov     rcx, rsi; CallbackData
0x1400145cc  call    cs:__imp_FltGetFileNameInformation
0x1400145d3  nop     dword ptr [rax+rax+00h]
0x1400145d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145df  cmp     rcx, r14
0x1400145e2  jz      short loc_140014643
0x1400145e4  mov     eax, [rcx+2Ch]
0x1400145e7  test    al, 10h
0x1400145e9  jz      short loc_140014643
0x1400145eb  cmp     byte ptr [rcx+29h], 4
0x1400145ef  jb      short loc_140014643
0x1400145f1  mov     rax, [rsp+0B8h+FileNameInformation]
0x1400145f6  lea     r9, NAME_NOT_AVAILABLE
0x1400145fd  test    rax, rax
0x140014600  jz      short loc_140014606
0x140014602  lea     r9, [rax+8]
0x140014606  mov     rax, [rbx+10h]
0x14001460a  movzx   edx, byte ptr [rbx+20h]
0x14001460e  mov     rcx, [rcx+18h]
0x140014612  mov     [rsp+0B8h+var_78], edx
0x140014616  movzx   r8d, byte ptr [rax+7Ch]
0x14001461b  add     rax, 58h ; 'X'
0x14001461f  mov     [rsp+0B8h+var_80], r8d
0x140014624  mov     [rsp+0B8h+var_88], rax
0x140014629  mov     rax, [rbp+20h]
0x14001462d  mov     [rsp+0B8h+LengthReturned], r9
0x140014632  lea     r9, aCreated; "Created"
0x140014639  mov     [rsp+0B8h+OldContext], rax
0x14001463e  call    WPP_SF_sqZ_guid_DD
0x140014643  mov     rcx, [rsp+0B8h+FileNameInformation]; FileNameInformation
0x140014648  test    rcx, rcx
0x14001464b  jz      loc_1400144D6
0x140014651  call    cs:__imp_FltReleaseFileNameInformation
0x140014658  nop     dword ptr [rax+rax+00h]
0x14001465d  jmp     loc_1400144D6
0x140014662  cmp     byte ptr [rcx+29h], 5
0x140014666  jb      loc_1400144FC
0x14001466c  mov     rcx, [rcx+18h]
0x140014670  mov     edx, 1Eh
0x140014675  xor     r9d, r9d
0x140014678  call    WPP_SF_D
0x14001467d  jmp     loc_1400144FC
```
