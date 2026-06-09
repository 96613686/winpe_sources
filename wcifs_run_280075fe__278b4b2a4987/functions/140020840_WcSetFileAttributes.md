# WcSetFileAttributes

- ea: `0x140020840`
- end: `0x140020982`
- name: `WcSetFileAttributes`
- size: `322`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x14002da54`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x140020840`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x1400208fc`
- `FLTMGR!FltSetInformationFile` at `0x1400208fc`
- `FLTMGR!FltQueryInformationFile` at `0x140020892`
- `FLTMGR!FltQueryInformationFile` at `0x140020892`

## pseudocode

```c
__int64 __fastcall WcSetFileAttributes(PFILE_OBJECT FileObject, PFLT_INSTANCE Instance)
{
  NTSTATUS v4; // eax
  int v5; // edx
  unsigned int v6; // ebx
  int v7; // r9d
  NTSTATUS v8; // eax
  char v10; // [rsp+30h] [rbp-48h]
  NTSTATUS v11; // [rsp+38h] [rbp-40h]
  __int128 FileInformation; // [rsp+40h] [rbp-38h] BYREF
  __int128 v13; // [rsp+50h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp-18h]

  FileInformation = 0;
  v13 = 0;
  v14 = 0;
  v4 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x28u, FileBasicInformation, 0);
  v6 = v4;
  if ( v4 >= 0 )
  {
    LODWORD(v14) = v14 | 1;
    FileInformation = 0;
    v13 = 0;
    v8 = FltSetInformationFile(Instance, FileObject, &FileInformation, 0x28u, FileBasicInformation);
    v6 = v8;
    if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = v8;
      v7 = 126;
      v10 = -33;
      goto LABEL_7;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = v4;
    v7 = 125;
    v10 = -53;
LABEL_7:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      15,
      v7,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v10,
      v11);
  }
  return v6;
}

```

## disassembly

```asm
0x140020840  mov     r11, rsp
0x140020843  mov     [r11+18h], rbx
0x140020847  mov     [r11+20h], rsi
0x14002084b  push    rdi
0x14002084c  sub     rsp, 70h
0x140020850  mov     rax, cs:__security_cookie
0x140020857  xor     rax, rsp
0x14002085a  mov     [rsp+78h+var_10], rax
0x14002085f  xor     eax, eax
0x140020861  lea     r8, [r11-38h]; FileInformation
0x140020865  mov     rsi, rdx
0x140020868  mov     [r11-50h], rax
0x14002086c  xorps   xmm0, xmm0
0x14002086f  mov     [rsp+78h+FileInformationClass], 4; FileInformationClass
0x140020877  mov     rdi, rcx
0x14002087a  mov     rdx, rcx; FileObject
0x14002087d  movups  [rsp+78h+FileInformation], xmm0
0x140020882  lea     r9d, [rax+28h]; Length
0x140020886  mov     rcx, rsi; Instance
0x140020889  movups  [rsp+78h+var_28], xmm0
0x14002088e  mov     [r11-18h], rax
0x140020892  call    cs:__imp_FltQueryInformationFile
0x140020899  nop     dword ptr [rax+rax+00h]
0x14002089e  mov     ebx, eax
0x1400208a0  test    eax, eax
0x1400208a2  jns     short loc_1400208CC
0x1400208a4  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400208ab  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400208b2  jz      loc_140020960
0x1400208b8  mov     [rsp+78h+var_40], eax
0x1400208bc  mov     r9d, 7Dh ; '}'
0x1400208c2  mov     dword ptr [rsp+78h+var_48], 10CBh
0x1400208ca  jmp     short loc_140020930
0x1400208cc  or      dword ptr [rsp+78h+var_18], 1
0x1400208d1  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x1400208d6  xorps   xmm0, xmm0
0x1400208d9  mov     [rsp+78h+FileInformationClass], 4; FileInformationClass
0x1400208e1  xorps   xmm1, xmm1
0x1400208e4  mov     r9d, 28h ; '('; Length
0x1400208ea  mov     rdx, rdi; FileObject
0x1400208ed  mov     rcx, rsi; Instance
0x1400208f0  movdqu  [rsp+78h+FileInformation], xmm0
0x1400208f6  movdqu  [rsp+78h+var_28], xmm1
0x1400208fc  call    cs:__imp_FltSetInformationFile
0x140020903  nop     dword ptr [rax+rax+00h]
0x140020908  mov     ebx, eax
0x14002090a  test    eax, eax
0x14002090c  jns     short loc_140020960
0x14002090e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140020915  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002091c  jz      short loc_140020960
0x14002091e  mov     [rsp+78h+var_40], eax
0x140020922  mov     r9d, 7Eh ; '~'
0x140020928  mov     dword ptr [rsp+78h+var_48], 10DFh
0x140020930  mov     rcx, cs:WPP_GLOBAL_Control
0x140020937  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002093e  mov     [rsp+78h+var_50], rax
0x140020943  mov     r8d, 0Fh
0x140020949  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140020950  mov     dl, 2
0x140020952  mov     qword ptr [rsp+78h+FileInformationClass], rax
0x140020957  mov     rcx, [rcx+40h]
0x14002095b  call    WPP_RECORDER_SF_sDd
0x140020960  mov     eax, ebx
0x140020962  mov     rcx, [rsp+78h+var_10]
0x140020967  xor     rcx, rsp; StackCookie
0x14002096a  call    __security_check_cookie
0x14002096f  lea     r11, [rsp+78h+var_8]
0x140020974  mov     rbx, [r11+20h]
0x140020978  mov     rsi, [r11+28h]
0x14002097c  mov     rsp, r11
0x14002097f  pop     rdi
0x140020980  retn
```
