# MpSendBlockProcessExecMessage

- ea: `0x14007af3c`
- end: `0x14007b125`
- name: `MpSendBlockProcessExecMessage`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140051af0`

## callees

- `0x1400051bc`
- `0x1400078a4`
- `0x1400118d0`
- `0x140034b50`
- `0x140035080`
- `0x140035e50`
- `0x14007af3c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14007b060`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14007b060`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b051`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b051`
- `FLTMGR!FltGetFileNameInformation` at `0x14007af82`
- `FLTMGR!FltGetFileNameInformation` at `0x14007af82`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007b0ef`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007b0ef`

## pseudocode

```c
__int64 __fastcall MpSendBlockProcessExecMessage(struct _FLT_CALLBACK_DATA *a1, int a2)
{
  NTSTATUS v3; // edi
  __int64 v4; // rdx
  int v5; // r14d
  unsigned int v6; // ebp
  _DWORD *v7; // rbx
  _DWORD *v9; // [rsp+30h] [rbp-38h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+38h] [rbp-30h] BYREF

  FileNameInformation = 0;
  if ( !a2 )
    return 0;
  v3 = FltGetFileNameInformation(a1, 0x102u, &FileNameInformation);
  if ( v3 >= 0 )
  {
    v9 = 0;
    v5 = FileNameInformation->Name.Length + 2;
    v6 = FileNameInformation->Name.Length + 42;
    v3 = MpAsyncCreateNotification(&v9, v6);
    if ( v3 >= 0 )
    {
      _mm_lfence();
      v7 = v9;
      memcpy_s(
        v9 + 10,
        FileNameInformation->Name.Length,
        FileNameInformation->Name.Buffer,
        FileNameInformation->Name.Length);
      *((_WORD *)v7 + ((unsigned __int64)FileNameInformation->Name.Length >> 1) + 20) = 0;
      v7[9] = v5;
      v7[8] = a2;
      v7[6] = (unsigned int)PsGetCurrentProcessId();
      v7[7] = (unsigned int)PsGetCurrentThreadId();
      v7[2] = v6;
      v7[4] = 20;
      v3 = MpAsyncSendNotification((_DWORD)v7, v6, 0, 1, 0);
      MpAsyncDereferenceNotification(v7);
      if ( v3 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v4 = 115;
        goto LABEL_15;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 114;
      goto LABEL_15;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v4 = 113;
LABEL_15:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
      KeGetCurrentThread(),
      v3);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14007af3c  mov     r11, rsp
0x14007af3f  mov     [r11+10h], rbx
0x14007af43  mov     [r11+18h], rbp
0x14007af47  mov     [r11+20h], rsi
0x14007af4b  push    rdi
0x14007af4c  push    r14
0x14007af4e  push    r15
0x14007af50  sub     rsp, 50h
0x14007af54  mov     rax, cs:__security_cookie
0x14007af5b  xor     rax, rsp
0x14007af5e  mov     [rsp+68h+var_28], rax
0x14007af63  xor     r15d, r15d
0x14007af66  mov     esi, edx
0x14007af68  mov     [r11-30h], r15
0x14007af6c  test    edx, edx
0x14007af6e  jnz     short loc_14007AF78
0x14007af70  mov     edi, r15d
0x14007af73  jmp     loc_14007B0FB
0x14007af78  lea     r8, [rsp+68h+FileNameInformation]; FileNameInformation
0x14007af7d  mov     edx, 102h; NameOptions
0x14007af82  call    cs:__imp_FltGetFileNameInformation
0x14007af89  nop     dword ptr [rax+rax+00h]
0x14007af8e  mov     edi, eax
0x14007af90  test    eax, eax
0x14007af92  jns     short loc_14007AFC1
0x14007af94  mov     rcx, cs:WPP_GLOBAL_Control
0x14007af9b  lea     rax, WPP_GLOBAL_Control
0x14007afa2  cmp     rcx, rax
0x14007afa5  jz      loc_14007B0E5
0x14007afab  mov     ecx, [rcx+2Ch]
0x14007afae  test    cl, 1
0x14007afb1  jz      loc_14007B0E5
0x14007afb7  mov     edx, 71h ; 'q'
0x14007afbc  jmp     loc_14007B0BE
0x14007afc1  mov     rax, [rsp+68h+FileNameInformation]
0x14007afc6  lea     rcx, [rsp+68h+var_38]
0x14007afcb  mov     [rsp+68h+var_38], r15
0x14007afd0  movzx   r14d, word ptr [rax+8]
0x14007afd5  add     r14d, 2
0x14007afd9  lea     ebp, [r14+28h]
0x14007afdd  mov     edx, ebp
0x14007afdf  call    MpAsyncCreateNotification
0x14007afe4  mov     edi, eax
0x14007afe6  test    eax, eax
0x14007afe8  jns     short loc_14007B016
0x14007afea  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aff1  lea     rax, WPP_GLOBAL_Control
0x14007aff8  cmp     rcx, rax
0x14007affb  jz      loc_14007B0E5
0x14007b001  mov     eax, [rcx+2Ch]
0x14007b004  test    al, 1
0x14007b006  jz      loc_14007B0E5
0x14007b00c  mov     edx, 72h ; 'r'
0x14007b011  jmp     loc_14007B0BE
0x14007b016  lfence
0x14007b019  mov     r8, [rsp+68h+FileNameInformation]
0x14007b01e  mov     rbx, [rsp+68h+var_38]
0x14007b023  movzx   edx, word ptr [r8+8]; DstSize
0x14007b028  mov     r8, [r8+10h]; Src
0x14007b02c  lea     rcx, [rbx+28h]; void *
0x14007b030  mov     r9d, edx; MaxCount
0x14007b033  call    memcpy_s
0x14007b038  mov     rax, [rsp+68h+FileNameInformation]
0x14007b03d  movzx   ecx, word ptr [rax+8]
0x14007b041  shr     rcx, 1
0x14007b044  mov     [rbx+rcx*2+28h], r15w
0x14007b04a  mov     [rbx+24h], r14d
0x14007b04e  mov     [rbx+20h], esi
0x14007b051  call    cs:__imp_PsGetCurrentProcessId
0x14007b058  nop     dword ptr [rax+rax+00h]
0x14007b05d  mov     [rbx+18h], eax
0x14007b060  call    cs:__imp_PsGetCurrentThreadId
0x14007b067  nop     dword ptr [rax+rax+00h]
0x14007b06c  mov     r9d, 1
0x14007b072  mov     [rsp+68h+var_48], r15
0x14007b077  mov     [rbx+1Ch], eax
0x14007b07a  xor     r8d, r8d
0x14007b07d  mov     [rbx+8], ebp
0x14007b080  mov     edx, ebp
0x14007b082  mov     rcx, rbx
0x14007b085  mov     dword ptr [rbx+10h], 14h
0x14007b08c  call    MpAsyncSendNotification
0x14007b091  mov     rcx, rbx
0x14007b094  mov     edi, eax
0x14007b096  call    MpAsyncDereferenceNotification
0x14007b09b  test    edi, edi
0x14007b09d  jns     short loc_14007B0E5
0x14007b09f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b0a6  lea     rax, WPP_GLOBAL_Control
0x14007b0ad  cmp     rcx, rax
0x14007b0b0  jz      short loc_14007B0E5
0x14007b0b2  mov     eax, [rcx+2Ch]
0x14007b0b5  test    al, 1
0x14007b0b7  jz      short loc_14007B0E5
0x14007b0b9  mov     edx, 73h ; 's'
0x14007b0be  lfence
0x14007b0c1  mov     r9, gs:188h
0x14007b0ca  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14007b0d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b0d8  mov     dword ptr [rsp+68h+var_48], edi
0x14007b0dc  mov     rcx, [rcx+18h]
0x14007b0e0  call    WPP_SF_qD
0x14007b0e5  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x14007b0ea  test    rcx, rcx
0x14007b0ed  jz      short loc_14007B0FB
0x14007b0ef  call    cs:__imp_FltReleaseFileNameInformation
0x14007b0f6  nop     dword ptr [rax+rax+00h]
0x14007b0fb  mov     eax, edi
0x14007b0fd  mov     rcx, [rsp+68h+var_28]
0x14007b102  xor     rcx, rsp; StackCookie
0x14007b105  call    __security_check_cookie
0x14007b10a  lea     r11, [rsp+68h+var_18]
0x14007b10f  mov     rbx, [r11+28h]
0x14007b113  mov     rbp, [r11+30h]
0x14007b117  mov     rsi, [r11+38h]
0x14007b11b  mov     rsp, r11
0x14007b11e  pop     r15
0x14007b120  pop     r14
0x14007b122  pop     rdi
0x14007b123  retn
```
