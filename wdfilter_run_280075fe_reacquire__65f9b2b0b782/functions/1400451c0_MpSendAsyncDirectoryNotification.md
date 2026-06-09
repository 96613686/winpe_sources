# MpSendAsyncDirectoryNotification

- ea: `0x1400451c0`
- end: `0x140045670`
- name: `MpSendAsyncDirectoryNotification`
- size: `1200`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1400036a0`
- `0x1400459c0`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x1400051bc`
- `0x1400118d0`
- `0x140030060`
- `0x140034b50`
- `0x140035080`
- `0x14003a1b0`
- `0x14003ba64`
- `0x1400443c0`
- `0x1400451c0`
- `0x140055520`

## import_xrefs

- `ntoskrnl!IoThreadToProcess` at `0x140045294`
- `ntoskrnl!IoThreadToProcess` at `0x1400452e1`
- `ntoskrnl!IoThreadToProcess` at `0x140045294`
- `ntoskrnl!IoThreadToProcess` at `0x1400452e1`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x1400453f7`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x1400453f7`
- `FLTMGR!FltReleaseContext` at `0x140045271`
- `FLTMGR!FltReleaseContext` at `0x140045605`
- `FLTMGR!FltReleaseContext` at `0x140045271`
- `FLTMGR!FltReleaseContext` at `0x140045605`
- `FLTMGR!FltGetInstanceContext` at `0x140045251`
- `FLTMGR!FltGetInstanceContext` at `0x1400455ec`
- `FLTMGR!FltGetInstanceContext` at `0x140045251`
- `FLTMGR!FltGetInstanceContext` at `0x1400455ec`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004538d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004538d`

## pseudocode

```c
NTSTATUS __fastcall MpSendAsyncDirectoryNotification(__int64 a1, __int64 a2, int a3, _BYTE *a4)
{
  struct _FLT_INSTANCE *v8; // rcx
  NTSTATUS result; // eax
  int v10; // r15d
  struct _KPROCESS *v11; // rdi
  struct _KPROCESS *v12; // rdi
  struct _KPROCESS *RequestorProcess; // rax
  NTSTATUS DestinationFileNameInformation; // edi
  struct _FLT_INSTANCE *v15; // rcx
  __int64 v16; // [rsp+70h] [rbp-78h]
  PFLT_CONTEXT v17; // [rsp+78h] [rbp-70h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp-68h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp-60h] BYREF

  if ( *(int *)(MpData + 3908) < 0 )
    return 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 == 4 )
  {
    if ( (*(_DWORD *)(MpData + 3908) & 4) == 0 )
      return 0;
  }
  else
  {
    if ( a3 != 2 )
      return -1073741811;
    if ( (*(_DWORD *)(MpData + 3908) & 2) == 0 )
      return 0;
  }
  if ( (*(_DWORD *)(MpData + 868) & 1) == 0 )
    return 0;
  v8 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  result = FltGetInstanceContext(v8, &Context);
  if ( result < 0 )
  {
    _mm_lfence();
    return result;
  }
  v10 = *((_DWORD *)Context + 21);
  FltReleaseContext(Context);
  v11 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v11 )
    return 0;
  v12 = *(struct _KPROCESS **)(MpData + 256);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v12 )
    return 0;
  _mm_lfence();
  v17 = 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
  if ( RequestorProcess
    && (int)MpGetProcessContextByObject(RequestorProcess) >= 0
    && (unsigned __int8)MpIsProcessExemptByContext(v17) )
  {
    return 0;
  }
  FileNameInformation = 0;
  if ( a3 != 2 )
    goto LABEL_14;
  if ( !v10 )
  {
    v15 = *(struct _FLT_INSTANCE **)(a2 + 24);
    v17 = 0;
    if ( FltGetInstanceContext(v15, &v17) >= 0 )
      FltReleaseContext(v17);
  }
  DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                     *(PFLT_INSTANCE *)(a2 + 24),
                                     *(PFILE_OBJECT *)(a2 + 32),
                                     *(HANDLE *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL) + 8LL),
                                     (PWSTR)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL) + 20LL),
                                     *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL) + 16LL),
                                     0x101u,
                                     &FileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_296cf4eb32a13e34549309923deeee07_Traceguids,
        KeGetCurrentThread(),
        DestinationFileNameInformation);
    }
  }
  else
  {
LABEL_14:
    MpGetFileAttributes(a2);
    v16 = 0;
    LODWORD(v17) = 0;
    DestinationFileNameInformation = 0;
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( a4 )
      *a4 = 1;
  }
  return DestinationFileNameInformation;
}

```

## disassembly

```asm
0x1400451c0  push    rbx
0x1400451c2  push    rbp
0x1400451c3  push    rsi
0x1400451c4  push    rdi
0x1400451c5  push    r12
0x1400451c7  push    r14
0x1400451c9  push    r15
0x1400451cb  sub     rsp, 0B0h
0x1400451d2  mov     rax, cs:__security_cookie
0x1400451d9  xor     rax, rsp
0x1400451dc  mov     [rsp+0E8h+var_58], rax
0x1400451e4  mov     rax, cs:MpData
0x1400451eb  mov     r14, rcx
0x1400451ee  mov     rsi, r9
0x1400451f1  mov     ebx, r8d
0x1400451f4  mov     rbp, rdx
0x1400451f7  mov     ecx, [rax+0F44h]
0x1400451fd  test    ecx, ecx
0x1400451ff  js      loc_1400452A5
0x140045205  test    r9, r9
0x140045208  jz      short loc_14004520E
0x14004520a  mov     byte ptr [r9], 0
0x14004520e  cmp     ebx, 4
0x140045211  jnz     loc_1400454D5
0x140045217  mov     rax, cs:MpData
0x14004521e  mov     ecx, [rax+0F44h]
0x140045224  test    bl, cl
0x140045226  jz      short loc_1400452A5
0x140045228  mov     rax, cs:MpData
0x14004522f  mov     ecx, [rax+364h]
0x140045235  test    cl, 1
0x140045238  jz      short loc_1400452A5
0x14004523a  mov     rcx, [rbp+18h]; Instance
0x14004523e  lea     rdx, [rsp+0E8h+Context]; Context
0x140045246  xor     r12d, r12d
0x140045249  mov     [rsp+0E8h+Context], r12
0x140045251  call    cs:__imp_FltGetInstanceContext
0x140045258  nop     dword ptr [rax+rax+00h]
0x14004525d  test    eax, eax
0x14004525f  js      loc_1400455D6
0x140045265  mov     rcx, [rsp+0E8h+Context]; Context
0x14004526d  mov     r15d, [rcx+54h]
0x140045271  call    cs:__imp_FltReleaseContext
0x140045278  nop     dword ptr [rax+rax+00h]
0x14004527d  mov     rcx, gs:188h; Thread
0x140045286  mov     rax, cs:MpData
0x14004528d  mov     rdi, [rax+0E8h]
0x140045294  call    cs:__imp_IoThreadToProcess
0x14004529b  nop     dword ptr [rax+rax+00h]
0x1400452a0  cmp     rax, rdi
0x1400452a3  jnz     short loc_1400452CA
0x1400452a5  xor     eax, eax
0x1400452a7  mov     rcx, [rsp+0E8h+var_58]
0x1400452af  xor     rcx, rsp; StackCookie
0x1400452b2  call    __security_check_cookie
0x1400452b7  add     rsp, 0B0h
0x1400452be  pop     r15
0x1400452c0  pop     r14
0x1400452c2  pop     r12
0x1400452c4  pop     rdi
0x1400452c5  pop     rsi
0x1400452c6  pop     rbp
0x1400452c7  pop     rbx
0x1400452c8  retn
0x1400452ca  mov     rcx, gs:188h; Thread
0x1400452d3  mov     rax, cs:MpData
0x1400452da  mov     rdi, [rax+100h]
0x1400452e1  call    cs:__imp_IoThreadToProcess
0x1400452e8  nop     dword ptr [rax+rax+00h]
0x1400452ed  cmp     rax, rdi
0x1400452f0  jz      short loc_1400452A5
0x1400452f2  mov     [rsp+0E8h+var_40], r13
0x1400452fa  lfence
0x1400452fd  mov     rcx, r14
0x140045300  mov     [rsp+0E8h+var_70], r12
0x140045305  mov     r13, r12
0x140045308  call    MpGetRequestorProcess
0x14004530d  test    rax, rax
0x140045310  jz      short loc_14004532C
0x140045312  lea     rdx, [rsp+0E8h+var_70]
0x140045317  mov     rcx, rax; Process
0x14004531a  call    MpGetProcessContextByObject
0x14004531f  mov     r13, [rsp+0E8h+var_70]
0x140045324  test    eax, eax
0x140045326  jns     loc_140045505
0x14004532c  mov     [rsp+0E8h+FileNameInformation], r12
0x140045334  mov     edi, 400h
0x140045339  cmp     ebx, 2
0x14004533c  jz      short loc_1400453B9
0x14004533e  mov     rcx, rbp
0x140045341  call    MpGetFileAttributes
0x140045346  mov     rcx, [rsp+0E8h+FileNameInformation]
0x14004534e  mov     r8d, eax
0x140045351  lea     rdx, [rcx+8]
0x140045355  test    rcx, rcx
0x140045358  jnz     short loc_14004535D
0x14004535a  mov     rdx, r12
0x14004535d  mov     rax, cs:MpData
0x140045364  mov     [rsp+0E8h+var_78], r12
0x140045369  mov     dword ptr [rsp+0E8h+var_70], r12d
0x14004536e  mov     ecx, [rax+364h]
0x140045374  test    cl, 1
0x140045377  jnz     loc_140045417
0x14004537d  mov     edi, r12d
0x140045380  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x140045388  test    rcx, rcx
0x14004538b  jz      short loc_140045399
0x14004538d  call    cs:__imp_FltReleaseFileNameInformation
0x140045394  nop     dword ptr [rax+rax+00h]
0x140045399  test    edi, edi
0x14004539b  jns     loc_14004565F
0x1400453a1  test    r13, r13
0x1400453a4  jnz     loc_1400454F8
0x1400453aa  mov     r13, [rsp+0E8h+var_40]
0x1400453b2  mov     eax, edi
0x1400453b4  jmp     loc_1400452A7
0x1400453b9  test    r15d, r15d
0x1400453bc  jz      loc_1400455DE
0x1400453c2  mov     rax, [r14+10h]
0x1400453c6  mov     rdx, [rbp+20h]; FileObject
0x1400453ca  mov     rcx, [rbp+18h]; Instance
0x1400453ce  mov     r8, [rax+38h]
0x1400453d2  lea     rax, [rsp+0E8h+FileNameInformation]
0x1400453da  mov     [rsp+0E8h+RetFileNameInformation], rax; RetFileNameInformation
0x1400453df  mov     [rsp+0E8h+NameOptions], 101h; NameOptions
0x1400453e7  mov     eax, [r8+10h]
0x1400453eb  lea     r9, [r8+14h]; FileName
0x1400453ef  mov     r8, [r8+8]; RootDirectory
0x1400453f3  mov     [rsp+0E8h+FileNameLength], eax; FileNameLength
0x1400453f7  call    cs:__imp_FltGetDestinationFileNameInformation
0x1400453fe  nop     dword ptr [rax+rax+00h]
0x140045403  mov     edi, eax
0x140045405  test    eax, eax
0x140045407  js      loc_140045566
0x14004540d  mov     edi, 0C00h
0x140045412  jmp     loc_14004533E
0x140045417  test    r13, r13
0x14004541a  jz      loc_14004537D
0x140045420  mov     ecx, [r13+34h]
0x140045424  test    cl, 8
0x140045427  jz      short loc_140045437
0x140045429  test    dword ptr [r13+38h], 4000h
0x140045431  jnz     loc_14004537D
0x140045437  test    cl, 1
0x14004543a  jnz     loc_1400455B9
0x140045440  mov     eax, [r13+38h]
0x140045444  test    al, 4
0x140045446  jnz     loc_14004537D
0x14004544c  mov     [rsp+0E8h+var_80], r12
0x140045451  lea     rcx, [rsp+0E8h+var_78]
0x140045456  mov     [rsp+0E8h+var_88], r13
0x14004545b  mov     r9, r14
0x14004545e  mov     [rsp+0E8h+var_90], r12
0x140045463  mov     [rsp+0E8h+var_98], r12
0x140045468  mov     [rsp+0E8h+var_A0], rdx
0x14004546d  lea     rdx, [rsp+0E8h+var_70]
0x140045472  mov     [rsp+0E8h+var_A8], r12
0x140045477  mov     [rsp+0E8h+var_B0], edi
0x14004547b  mov     dword ptr [rsp+0E8h+RetFileNameInformation], r8d
0x140045480  mov     r8d, ebx
0x140045483  mov     [rsp+0E8h+NameOptions], r15d
0x140045488  mov     qword ptr [rsp+0E8h+FileNameLength], rbp
0x14004548d  call    MpCreateFileAsyncMessage
0x140045492  mov     edi, eax
0x140045494  test    eax, eax
0x140045496  js      loc_14004551D
0x14004549c  lfence
0x14004549f  mov     rbx, [rsp+0E8h+var_78]
0x1400454a4  mov     r9d, 0FFFFFFFFh
0x1400454aa  mov     edx, dword ptr [rsp+0E8h+var_70]
0x1400454ae  mov     rcx, rbx
0x1400454b1  xor     r8d, r8d
0x1400454b4  mov     qword ptr [rsp+0E8h+FileNameLength], r13
0x1400454b9  call    MpAsyncSendNotification
0x1400454be  mov     edi, eax
0x1400454c0  test    eax, eax
0x1400454c2  js      loc_140045616
0x1400454c8  mov     rcx, rbx
0x1400454cb  call    MpAsyncDereferenceNotification
0x1400454d0  jmp     loc_140045380
0x1400454d5  cmp     ebx, 2
0x1400454d8  jnz     loc_1400455CC
0x1400454de  mov     rax, cs:MpData
0x1400454e5  mov     ecx, [rax+0F44h]
0x1400454eb  test    bl, cl
0x1400454ed  jz      loc_1400452A5
0x1400454f3  jmp     loc_140045228
0x1400454f8  mov     rcx, r13
0x1400454fb  call    MpReleaseProcessContext
0x140045500  jmp     loc_1400453AA
0x140045505  mov     rcx, r13
0x140045508  call    MpIsProcessExemptByContext
0x14004550d  test    al, al
0x14004550f  jz      loc_14004532C
0x140045515  mov     edi, r12d
0x140045518  jmp     loc_1400453A1
0x14004551d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045524  lea     rax, WPP_GLOBAL_Control
0x14004552b  cmp     rcx, rax
0x14004552e  jz      loc_140045380
0x140045534  mov     eax, [rcx+2Ch]
0x140045537  test    al, 4
0x140045539  jz      loc_140045380
0x14004553f  lfence
0x140045542  mov     rcx, cs:WPP_GLOBAL_Control
0x140045549  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x140045550  mov     edx, 3Eh ; '>'
0x140045555  mov     r9d, edi
0x140045558  mov     rcx, [rcx+18h]
0x14004555c  call    WPP_SF_d
0x140045561  jmp     loc_140045380
0x140045566  mov     rcx, cs:WPP_GLOBAL_Control
0x14004556d  lea     rax, WPP_GLOBAL_Control
0x140045574  cmp     rcx, rax
0x140045577  jz      loc_1400453A1
0x14004557d  mov     eax, [rcx+2Ch]
0x140045580  test    al, 1
0x140045582  jz      loc_1400453A1
0x140045588  lfence
0x14004558b  mov     r9, gs:188h
0x140045594  lea     r8, WPP_296cf4eb32a13e34549309923deeee07_Traceguids
0x14004559b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400455a2  mov     edx, 0Dh
0x1400455a7  mov     [rsp+0E8h+FileNameLength], edi
0x1400455ab  mov     rcx, [rcx+18h]
0x1400455af  call    WPP_SF_qD
0x1400455b4  jmp     loc_1400453A1
0x1400455b9  test    dword ptr [r13+38h], 4000h
0x1400455c1  jnz     loc_140045440
0x1400455c7  jmp     loc_14004537D
0x1400455cc  mov     eax, 0C000000Dh
0x1400455d1  jmp     loc_1400452A7
0x1400455d6  lfence
0x1400455d9  jmp     loc_1400452A7
0x1400455de  mov     rcx, [rbp+18h]; Instance
0x1400455e2  lea     rdx, [rsp+0E8h+var_70]; Context
0x1400455e7  mov     [rsp+0E8h+var_70], r12
0x1400455ec  call    cs:__imp_FltGetInstanceContext
0x1400455f3  nop     dword ptr [rax+rax+00h]
0x1400455f8  test    eax, eax
0x1400455fa  js      loc_1400453C2
0x140045600  mov     rcx, [rsp+0E8h+var_70]; Context
0x140045605  call    cs:__imp_FltReleaseContext
0x14004560c  nop     dword ptr [rax+rax+00h]
0x140045611  jmp     loc_1400453C2
0x140045616  mov     rcx, cs:WPP_GLOBAL_Control
0x14004561d  lea     rax, WPP_GLOBAL_Control
0x140045624  cmp     rcx, rax
0x140045627  jz      loc_1400454C8
0x14004562d  mov     eax, [rcx+2Ch]
0x140045630  test    al, 4
0x140045632  jz      loc_1400454C8
0x140045638  lfence
0x14004563b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045642  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x140045649  mov     edx, 3Fh ; '?'
0x14004564e  mov     r9d, edi
0x140045651  mov     rcx, [rcx+18h]
0x140045655  call    WPP_SF_d
0x14004565a  jmp     loc_1400454C8
0x14004565f  test    rsi, rsi
0x140045662  jz      loc_1400453A1
0x140045668  mov     byte ptr [rsi], 1
0x14004566b  jmp     loc_1400453A1
```
