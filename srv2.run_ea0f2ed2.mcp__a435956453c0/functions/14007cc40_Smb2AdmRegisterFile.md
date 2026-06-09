# Smb2AdmRegisterFile

- ea: `0x14007cc40`
- end: `0x14007d0a3`
- name: `Smb2AdmRegisterFile`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14007a89c`

## callees

- `0x140013810`
- `0x140013920`
- `0x140016d30`
- `0x1400224b8`
- `0x14002a410`
- `0x140038490`
- `0x140038980`
- `0x140063bf4`
- `0x140077390`
- `0x14007cc40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007cfc1`
- `ntoskrnl!ExAllocatePool2` at `0x14007cfc1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007cf2f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098482`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007cf2f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098482`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007cf09`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098462`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007cf09`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cf86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cf86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cff1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007cd73`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007cd73`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14007cd3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14007cd3a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007cfa2`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007cfa2`
- `srvnet!SrvAdminRegisterFile` at `0x14007ce1f`
- `srvnet!SrvAdminRegisterFile` at `0x14007ce1f`

## pseudocode

```c
__int64 __fastcall Smb2AdmRegisterFile(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  volatile signed __int64 *v3; // r12
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  int v8; // r8d
  __int64 v9; // rdi
  unsigned int v10; // esi
  PVOID v11; // rbx
  __int64 v12; // rcx
  USHORT Length; // ax
  __int64 v14; // rsi
  bool v15; // cf
  const UNICODE_STRING *v16; // rsi
  unsigned __int16 v17; // dx
  unsigned __int16 v18; // cx
  WCHAR *Pool2; // rax
  char v20; // r10
  char v21; // dl
  signed __int64 v22; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  volatile signed __int64 **v26; // rdi
  volatile signed __int64 *v28; // r14
  volatile signed __int64 *v29; // r15
  signed __int64 v30; // r13
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 *v33; // rax
  struct _ERESOURCE *v34; // rcx
  struct _ERESOURCE *v35; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[1024]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = 0;
  v39 = a3;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v37 = 0;
  P = 0;
  v6 = Smb2ReferenceSessionAndTreeConnectFromFile(a1, &v37, &P);
  v9 = v37;
  v10 = v6;
  v11 = P;
  if ( v6 < 0 )
    goto LABEL_18;
  v12 = *(_QWORD *)(a1 + 128);
  Length = a2->Length;
  v14 = 152;
  v15 = *(_WORD *)(v12 + 152) < 6u;
  DestinationString.MaximumLength = 0;
  if ( v15 )
    v14 = 120;
  v16 = (const UNICODE_STRING *)(v12 + v14);
  v17 = v16->Length + Length;
  if ( v17 < Length )
  {
    v10 = -1073741675;
    DestinationString.MaximumLength = -1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_18;
    }
    v24 = 17;
LABEL_60:
    WPP_SF_d(v7->AttachedDevice, v24, &WPP_026a9657692237905df4630b7666c8cd_Traceguids, 3221225621LL);
    goto LABEL_18;
  }
  v18 = v17 + 2;
  if ( (unsigned __int16)(v17 + 2) < v17 )
  {
    v10 = -1073741675;
    DestinationString.MaximumLength = -1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_18;
    }
    v24 = 18;
    goto LABEL_60;
  }
  DestinationString.MaximumLength = v17 + 2;
  DestinationString.Length = 0;
  if ( v18 > 0x200u )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, v18, 1647465292);
    DestinationString.Buffer = Pool2;
    LODWORD(v7) = 1;
    if ( Pool2 )
      LODWORD(v3) = 1;
  }
  else
  {
    DestinationString.Buffer = (PWSTR)v40;
    memset(v40, 0, sizeof(v40));
    Pool2 = (WCHAR *)v40;
  }
  if ( Pool2 )
  {
    RtlCopyUnicodeString(&DestinationString, v16);
    if ( !DestinationString.Length
      || DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92 )
    {
      RtlAppendUnicodeToString(&DestinationString, L"\\");
    }
    RtlAppendUnicodeStringToString(&DestinationString, a2);
    if ( *((_BYTE *)v11 + 90) || *(_BYTE *)(v9 + 59) )
    {
      v21 = 1;
      v20 = 0;
    }
    else
    {
      v20 = *(_BYTE *)(v9 + 57);
      v21 = 0;
    }
    v10 = SrvAdminRegisterFile(
            &DestinationString,
            *(unsigned int *)(a1 + 184),
            a1 + 248,
            *(_QWORD *)(v9 + 64),
            *(_DWORD *)(*(_QWORD *)(a1 + 128) + 356LL),
            Smb2ProviderId,
            -1,
            *(_QWORD *)(a1 + 80),
            *(_BYTE *)(v39 + 380),
            *(_BYTE *)(v9 + 285),
            v21,
            v20,
            *(_BYTE *)(v39 + 309),
            a1 + 320,
            **(unsigned __int8 **)(a1 + 64));
    Pool2 = DestinationString.Buffer;
  }
  else
  {
    v10 = -1073741670;
  }
  if ( (_DWORD)v3 == 1 )
    ExFreePoolWithTag(Pool2, 0);
  v3 = 0;
LABEL_18:
  if ( v9 )
    Smb2DereferenceSession(v9);
  if ( v11 )
  {
    v22 = _InterlockedDecrement64((volatile signed __int64 *)v11);
    if ( v22 == -1 )
    {
      __int2c();
    }
    else if ( !v22 )
    {
      if ( (byte_14004C339 & 1) != 0 )
      {
        v32 = *((_QWORD *)v11 + 14);
        if ( v32 )
          v33 = (__int64 *)(v32 + 72);
        else
          v33 = &Srv2ZeroGuid;
        McTemplateK0jj_EtwWriteTransfer(
          (_DWORD)v7,
          (unsigned int)&SMB2_EVENT_TREECONNECT_TERMINATE,
          v8,
          (_DWORD)v11 + 24,
          (__int64)v33);
      }
      v25 = *((_QWORD *)v11 + 14);
      if ( v25 )
        Smb2DereferenceSession(v25);
      v26 = (volatile signed __int64 **)*((_QWORD *)v11 + 12);
      if ( v26 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(*v26 + 12), 1u);
        if ( (*((_DWORD *)v26 + 50))-- == 1 )
        {
          v3 = v26[40];
          v34 = (struct _ERESOURCE *)(*v26 + 25);
          v29 = v26[39];
          v28 = v26[41];
          v26[40] = 0;
          v26[39] = 0;
          v26[41] = 0;
          ExAcquireResourceExclusiveLite(v34, 1u);
          v35 = (struct _ERESOURCE *)(*v26 + 25);
          *((_DWORD *)v26 + 88) = 0;
          ExReleaseResourceLite(v35);
        }
        else
        {
          v28 = 0;
          v29 = 0;
        }
        ExReleaseResourceLite((PERESOURCE)(*v26 + 12));
        v30 = _InterlockedDecrement64(*v26);
        if ( v30 == -1 )
        {
          __int2c();
        }
        else if ( !v30 )
        {
          Smb2FreeShare((char *)v26);
        }
        if ( v3 )
          Smb2DereferenceHandle((PVOID)v3);
        if ( v29 )
          Smb2DereferenceHandle((PVOID)v29);
        if ( v28 )
          Smb2DereferenceHandle((PVOID)v28);
      }
      v31 = *((_QWORD *)v11 + 15);
      if ( v31 )
        Smb2DereferenceSecurityContext(v31);
      ExFreePoolWithTag(v11, 0);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14007cc40  mov     [rsp-8+arg_18], rbx
0x14007cc45  push    rbp
0x14007cc46  push    rsi
0x14007cc47  push    rdi
0x14007cc48  push    r12
0x14007cc4a  push    r13
0x14007cc4c  push    r14
0x14007cc4e  push    r15
0x14007cc50  lea     rbp, [rsp-3C0h]
0x14007cc58  sub     rsp, 4C0h
0x14007cc5f  mov     rax, cs:__security_cookie
0x14007cc66  xor     rax, rsp
0x14007cc69  mov     [rbp+3F0h+var_40], rax
0x14007cc70  xor     r12d, r12d
0x14007cc73  mov     [rbp+3F0h+var_450], r8
0x14007cc77  mov     r15, rdx
0x14007cc7a  mov     qword ptr [rbp+3F0h+DestinationString.Length], r12
0x14007cc7e  lea     r8, [rbp+3F0h+P]
0x14007cc82  mov     [rbp+3F0h+DestinationString.Buffer], r12
0x14007cc86  lea     rdx, [rbp+3F0h+var_460]
0x14007cc8a  mov     [rbp+3F0h+var_460], r12
0x14007cc8e  mov     [rbp+3F0h+P], r12
0x14007cc92  mov     r14, rcx
0x14007cc95  call    Smb2ReferenceSessionAndTreeConnectFromFile
0x14007cc9a  mov     rdi, [rbp+3F0h+var_460]
0x14007cc9e  mov     esi, eax
0x14007cca0  mov     rbx, [rbp+3F0h+P]
0x14007cca4  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14007ccab  test    eax, eax
0x14007ccad  js      loc_14007CE3E
0x14007ccb3  mov     rcx, [r14+80h]
0x14007ccba  mov     edx, 78h ; 'x'
0x14007ccbf  movzx   eax, word ptr [r15]
0x14007ccc3  mov     esi, 98h
0x14007ccc8  cmp     word ptr [rcx+98h], 6
0x14007ccd0  mov     [rbp+3F0h+DestinationString.MaximumLength], r12w
0x14007ccd5  cmovb   esi, edx
0x14007ccd8  movzx   edx, ax
0x14007ccdb  add     rsi, rcx
0x14007ccde  add     dx, [rsi]
0x14007cce1  cmp     dx, ax
0x14007cce4  jb      loc_14007CE96
0x14007ccea  lea     ecx, [rdx+2]
0x14007cced  cmp     cx, dx
0x14007ccf0  jb      loc_14007D002
0x14007ccf6  mov     eax, 200h
0x14007ccfb  mov     [rbp+3F0h+DestinationString.MaximumLength], cx
0x14007ccff  mov     [rbp+3F0h+DestinationString.Length], r12w
0x14007cd04  cmp     cx, ax
0x14007cd07  ja      loc_14007CFB3
0x14007cd0d  lea     rax, [rbp+3F0h+var_440]
0x14007cd11  xor     edx, edx; Val
0x14007cd13  mov     r8d, 400h; Size
0x14007cd19  mov     [rbp+3F0h+DestinationString.Buffer], rax
0x14007cd1d  lea     rcx, [rbp+3F0h+var_440]; void *
0x14007cd21  call    memset
0x14007cd26  mov     rax, [rbp+3F0h+DestinationString.Buffer]
0x14007cd2a  test    rax, rax
0x14007cd2d  jz      loc_14007CFE2
0x14007cd33  mov     rdx, rsi; SourceString
0x14007cd36  lea     rcx, [rbp+3F0h+DestinationString]; DestinationString
0x14007cd3a  call    cs:__imp_RtlCopyUnicodeString
0x14007cd41  nop     dword ptr [rax+rax+00h]
0x14007cd46  movzx   ecx, [rbp+3F0h+DestinationString.Length]
0x14007cd4a  xor     eax, eax
0x14007cd4c  cmp     ax, cx
0x14007cd4f  jz      loc_14007CF97
0x14007cd55  mov     rax, [rbp+3F0h+DestinationString.Buffer]
0x14007cd59  mov     edx, 5Ch ; '\'
0x14007cd5e  shr     rcx, 1
0x14007cd61  cmp     dx, [rax+rcx*2-2]
0x14007cd66  jnz     loc_14007CF97
0x14007cd6c  mov     rdx, r15; Source
0x14007cd6f  lea     rcx, [rbp+3F0h+DestinationString]; Destination
0x14007cd73  call    cs:__imp_RtlAppendUnicodeStringToString
0x14007cd7a  nop     dword ptr [rax+rax+00h]
0x14007cd7f  cmp     byte ptr [rbx+5Ah], 0
0x14007cd83  jnz     loc_14007CED2
0x14007cd89  cmp     byte ptr [rdi+3Bh], 0
0x14007cd8d  jnz     loc_14007CED2
0x14007cd93  movzx   r10d, byte ptr [rdi+39h]
0x14007cd98  xor     dl, dl
0x14007cd9a  mov     rax, [r14+40h]
0x14007cd9e  lea     r8, [r14+0F8h]
0x14007cda5  mov     r9, [r14+80h]
0x14007cdac  movzx   ecx, byte ptr [rax]
0x14007cdaf  lea     rax, [r14+140h]
0x14007cdb6  mov     [rsp+4F0h+var_480], ecx
0x14007cdba  mov     rcx, [rbp+3F0h+var_450]
0x14007cdbe  mov     [rsp+4F0h+var_488], rax
0x14007cdc3  movzx   eax, byte ptr [rcx+135h]
0x14007cdca  mov     [rsp+4F0h+var_490], al
0x14007cdce  movzx   eax, byte ptr [rdi+11Dh]
0x14007cdd5  mov     [rsp+4F0h+var_498], r10b
0x14007cdda  mov     [rsp+4F0h+var_4A0], dl
0x14007cdde  mov     edx, [r14+0B8h]
0x14007cde5  mov     [rsp+4F0h+var_4A8], al
0x14007cde9  movzx   eax, byte ptr [rcx+17Ch]
0x14007cdf0  lea     rcx, [rbp+3F0h+DestinationString]
0x14007cdf4  mov     [rsp+4F0h+var_4B0], al
0x14007cdf8  mov     rax, [r14+50h]
0x14007cdfc  mov     [rsp+4F0h+var_4B8], rax
0x14007ce01  mov     eax, cs:Smb2ProviderId
0x14007ce07  mov     [rsp+4F0h+var_4C0], r13
0x14007ce0c  mov     [rsp+4F0h+var_4C8], eax
0x14007ce10  mov     eax, [r9+164h]
0x14007ce17  mov     r9, [rdi+40h]
0x14007ce1b  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x14007ce1f  call    cs:__imp_SrvAdminRegisterFile
0x14007ce26  nop     dword ptr [rax+rax+00h]
0x14007ce2b  mov     esi, eax
0x14007ce2d  mov     rax, [rbp+3F0h+DestinationString.Buffer]
0x14007ce31  cmp     r12d, 1
0x14007ce35  jz      loc_14007CFEC
0x14007ce3b  xor     r12d, r12d
0x14007ce3e  test    rdi, rdi
0x14007ce41  jz      short loc_14007CE4B
0x14007ce43  mov     rcx, rdi
0x14007ce46  call    Smb2DereferenceSession
0x14007ce4b  test    rbx, rbx
0x14007ce4e  jz      short loc_14007CE69
0x14007ce50  mov     rax, r13
0x14007ce53  lock xadd [rbx], rax
0x14007ce58  dec     rax
0x14007ce5b  cmp     rax, r13
0x14007ce5e  jnb     loc_14007D041
0x14007ce64  test    rax, rax
0x14007ce67  jz      short loc_14007CEDC
0x14007ce69  mov     eax, esi
0x14007ce6b  mov     rcx, [rbp+3F0h+var_40]
0x14007ce72  xor     rcx, rsp; StackCookie
0x14007ce75  call    __security_check_cookie
0x14007ce7a  mov     rbx, [rsp+4F0h+arg_18]
0x14007ce82  add     rsp, 4C0h
0x14007ce89  pop     r15
0x14007ce8b  pop     r14
0x14007ce8d  pop     r13
0x14007ce8f  pop     r12
0x14007ce91  pop     rdi
0x14007ce92  pop     rsi
0x14007ce93  pop     rbp
0x14007ce94  retn
0x14007ce96  mov     eax, 0FFFFh
0x14007ce9b  mov     esi, 0C0000095h
0x14007cea0  mov     [rbp+3F0h+DestinationString.MaximumLength], ax
0x14007cea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ceab  lea     rax, WPP_GLOBAL_Control
0x14007ceb2  cmp     rcx, rax
0x14007ceb5  jz      short loc_14007CE3E
0x14007ceb7  mov     eax, [rcx+2Ch]
0x14007ceba  test    al, 1
0x14007cebc  jz      short loc_14007CE3E
0x14007cebe  cmp     byte ptr [rcx+29h], 1
0x14007cec2  jb      loc_14007CE3E
0x14007cec8  mov     edx, 11h
0x14007cecd  jmp     loc_1400983E5
0x14007ced2  mov     dl, 1
0x14007ced4  xor     r10b, r10b
0x14007ced7  jmp     loc_14007CD9A
0x14007cedc  test    cs:byte_14004C339, 1
0x14007cee3  jnz     loc_14007D048
0x14007cee9  mov     rcx, [rbx+70h]
0x14007ceed  test    rcx, rcx
0x14007cef0  jz      short loc_14007CEF7
0x14007cef2  call    Smb2DereferenceSession
0x14007cef7  mov     rdi, [rbx+60h]
0x14007cefb  test    rdi, rdi
0x14007cefe  jz      short loc_14007CF74
0x14007cf00  mov     rcx, [rdi]
0x14007cf03  mov     dl, 1; Wait
0x14007cf05  add     rcx, 60h ; '`'; Resource
0x14007cf09  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14007cf10  nop     dword ptr [rax+rax+00h]
0x14007cf15  add     dword ptr [rdi+0C8h], 0FFFFFFFFh
0x14007cf1c  jz      loc_140098420
0x14007cf22  xor     r14d, r14d
0x14007cf25  xor     r15d, r15d
0x14007cf28  mov     rcx, [rdi]
0x14007cf2b  add     rcx, 60h ; '`'; Resource
0x14007cf2f  call    cs:__imp_ExReleaseResourceLite
0x14007cf36  nop     dword ptr [rax+rax+00h]
0x14007cf3b  mov     rax, [rdi]
0x14007cf3e  lock xadd [rax], r13
0x14007cf43  dec     r13
0x14007cf46  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x14007cf4a  jnb     loc_14007D05E
0x14007cf50  test    r13, r13
0x14007cf53  jz      loc_14007D065
0x14007cf59  test    r12, r12
0x14007cf5c  jnz     loc_14007D072
0x14007cf62  test    r15, r15
0x14007cf65  jnz     loc_14007D07F
0x14007cf6b  test    r14, r14
0x14007cf6e  jnz     loc_14007D08C
0x14007cf74  mov     rcx, [rbx+78h]
0x14007cf78  test    rcx, rcx
0x14007cf7b  jnz     loc_14007D099
0x14007cf81  xor     edx, edx; Tag
0x14007cf83  mov     rcx, rbx; P
0x14007cf86  call    cs:__imp_ExFreePoolWithTag
0x14007cf8d  nop     dword ptr [rax+rax+00h]
0x14007cf92  jmp     loc_14007CE69
0x14007cf97  lea     rdx, Source; "\\"
0x14007cf9e  lea     rcx, [rbp+3F0h+DestinationString]; Destination
0x14007cfa2  call    cs:__imp_RtlAppendUnicodeToString
0x14007cfa9  nop     dword ptr [rax+rax+00h]
0x14007cfae  jmp     loc_14007CD6C
0x14007cfb3  movzx   edx, cx
0x14007cfb6  mov     r8d, 6232534Ch
0x14007cfbc  mov     ecx, 100h
0x14007cfc1  call    cs:__imp_ExAllocatePool2
0x14007cfc8  nop     dword ptr [rax+rax+00h]
0x14007cfcd  test    rax, rax
0x14007cfd0  mov     [rbp+3F0h+DestinationString.Buffer], rax
0x14007cfd4  mov     ecx, 1
0x14007cfd9  cmovnz  r12d, ecx
0x14007cfdd  jmp     loc_14007CD2A
0x14007cfe2  mov     esi, 0C000009Ah
0x14007cfe7  jmp     loc_14007CE31
0x14007cfec  xor     edx, edx; Tag
0x14007cfee  mov     rcx, rax; P
0x14007cff1  call    cs:__imp_ExFreePoolWithTag
0x14007cff8  nop     dword ptr [rax+rax+00h]
0x14007cffd  jmp     loc_14007CE3B
0x14007d002  mov     eax, 0FFFFh
0x14007d007  mov     esi, 0C0000095h
0x14007d00c  mov     [rbp+3F0h+DestinationString.MaximumLength], ax
0x14007d010  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d017  lea     rax, WPP_GLOBAL_Control
0x14007d01e  cmp     rcx, rax
0x14007d021  jz      loc_14007CE3E
0x14007d027  mov     eax, [rcx+2Ch]
0x14007d02a  test    al, 1
0x14007d02c  jz      loc_14007CE3E
0x14007d032  cmp     byte ptr [rcx+29h], 1
0x14007d036  jb      loc_14007CE3E
0x14007d03c  jmp     loc_1400983E0
0x14007d041  int     2Ch; Windows NT - assertion failure
0x14007d043  jmp     loc_14007CE69
0x14007d048  mov     rax, [rbx+70h]
0x14007d04c  test    rax, rax
0x14007d04f  jz      loc_1400983FE
0x14007d055  add     rax, 48h ; 'H'
0x14007d059  jmp     loc_140098405
0x14007d05e  int     2Ch; Windows NT - assertion failure
0x14007d060  jmp     loc_14007CF59
0x14007d065  mov     rcx, rdi; P
0x14007d068  call    Smb2FreeShare
0x14007d06d  jmp     loc_14007CF59
0x14007d072  mov     rcx, r12; P
0x14007d075  call    Smb2DereferenceHandle
0x14007d07a  jmp     loc_14007CF62
0x14007d07f  mov     rcx, r15; P
0x14007d082  call    Smb2DereferenceHandle
0x14007d087  jmp     loc_14007CF6B
0x14007d08c  mov     rcx, r14; P
0x14007d08f  call    Smb2DereferenceHandle
0x14007d094  jmp     loc_14007CF74
0x14007d099  call    Smb2DereferenceSecurityContext
0x14007d09e  jmp     loc_14007CF81
0x1400983e0  mov     edx, 12h
0x1400983e5  mov     rcx, [rcx+18h]
0x1400983e9  lea     r8, WPP_026a9657692237905df4630b7666c8cd_Traceguids
0x1400983f0  mov     r9d, esi
0x1400983f3  call    WPP_SF_d
0x1400983f8  nop
0x1400983f9  jmp     loc_14007CE3E
0x1400983fe  lea     rax, Srv2ZeroGuid
0x140098405  lea     r9, [rbx+18h]
0x140098409  mov     [rsp+4F0h+var_4D0], rax
0x14009840e  lea     rdx, SMB2_EVENT_TREECONNECT_TERMINATE
0x140098415  call    McTemplateK0jj_EtwWriteTransfer
0x14009841a  nop
0x14009841b  jmp     loc_14007CEE9
0x140098420  mov     rcx, [rdi]
0x140098423  mov     dl, 1; Wait
0x140098425  mov     r12, [rdi+140h]
0x14009842c  add     rcx, 0C8h; Resource
0x140098433  mov     r15, [rdi+138h]
0x14009843a  mov     r14, [rdi+148h]
0x140098441  mov     qword ptr [rdi+140h], 0
0x14009844c  mov     qword ptr [rdi+138h], 0
0x140098457  mov     qword ptr [rdi+148h], 0
0x140098462  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140098469  nop     dword ptr [rax+rax+00h]
0x14009846e  mov     rcx, [rdi]
0x140098471  add     rcx, 0C8h; Resource
0x140098478  mov     dword ptr [rdi+160h], 0
0x140098482  call    cs:__imp_ExReleaseResourceLite
0x140098489  nop     dword ptr [rax+rax+00h]
0x14009848e  nop
0x14009848f  jmp     loc_14007CF28
```
