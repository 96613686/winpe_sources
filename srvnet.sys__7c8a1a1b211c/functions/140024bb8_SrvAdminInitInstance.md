# SrvAdminInitInstance

- ea: `0x140024bb8`
- end: `0x140025021`
- name: `SrvAdminInitInstance`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400251a0`

## callees

- `0x1400054f0`
- `0x140007c60`
- `0x14000f780`
- `0x1400103a8`
- `0x14001389c`
- `0x1400163d8`
- `0x140016450`
- `0x140018480`
- `0x140024bb8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140024d06`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140024d1a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140024d06`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140024d1a`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140024f18`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140024f18`
- `ntoskrnl!ExInitializeResourceLite` at `0x140024f28`
- `ntoskrnl!ExInitializeResourceLite` at `0x140024f3b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140024f4e`
- `ntoskrnl!ExInitializeResourceLite` at `0x140024f28`
- `ntoskrnl!ExInitializeResourceLite` at `0x140024f3b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140024f4e`

## pseudocode

```c
__int64 __fastcall SrvAdminInitInstance(unsigned int a1, __int64 *a2)
{
  __int64 v4; // rsi
  __int64 *v5; // r14
  __int64 *v6; // r15
  __int64 PoolWithTag; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // r8
  struct _UNICODE_STRING *v11; // rcx
  __int16 v12; // ax
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rax
  int v16; // ecx
  int v17; // r8d
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // ecx
  int v22; // r8d
  __int64 v23; // rax
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // rax
  bool v27; // zf
  __int64 *v28; // rax
  _DWORD v29[4]; // [rsp+30h] [rbp-30h] BYREF
  _DWORD v30[4]; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v31[4]; // [rsp+50h] [rbp-10h] BYREF
  int v32; // [rsp+A0h] [rbp+40h] BYREF
  int v33; // [rsp+A4h] [rbp+44h]

  v29[0] = 8;
  v29[1] = 8;
  v29[2] = 8;
  v30[1] = 8;
  v30[2] = 8;
  v31[0] = 9;
  v31[1] = 9;
  v31[2] = 9;
  v32 = 10;
  v33 = 10;
  v30[0] = 10;
  if ( a1 < 6 )
  {
    v4 = 7LL * a1;
    v5 = &qword_140036198[v4];
    v6 = &SrvAdminInstanceNames[v4];
    PoolWithTag = SrvNetAllocatePoolWithTag(
                    64,
                    LOWORD(SrvAdminInstanceNames[v4 + 5]) + 536LL + LOWORD(qword_140036198[v4]),
                    1684095315);
    v8 = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, v5);
      }
      return (unsigned int)-1073741670;
    }
    v10 = *(unsigned __int16 *)v5;
    v11 = (struct _UNICODE_STRING *)(PoolWithTag + 32);
    *(_WORD *)(PoolWithTag + 34) = v10;
    *(_WORD *)(PoolWithTag + 32) = v10;
    *(_QWORD *)(PoolWithTag + 40) = PoolWithTag + 528;
    v12 = *((_WORD *)v6 + 20);
    *(_WORD *)(v8 + 50) = v12;
    *(_WORD *)(v8 + 48) = v12;
    *(_QWORD *)(v8 + 56) = v8 + 2 * (v10 + 264);
    RtlCopyUnicodeString(v11, (PCUNICODE_STRING)&qword_140036198[v4]);
    RtlCopyUnicodeString((PUNICODE_STRING)(v8 + 48), (PCUNICODE_STRING)(v6 + 5));
    *(_DWORD *)(v8 + 24) = 1;
    *(_DWORD *)(v8 + 28) = 1;
    *(_BYTE *)(v8 + 16) = SrvAdminInstanceNames[v4];
    v15 = RfsTable64Create(v13, (unsigned int)v29, v14, 8, (__int64)SrvAdminReferenceSession);
    *(_QWORD *)(v8 + 64) = v15;
    if ( v15 )
    {
      v20 = RfsTableCreate(v16, (unsigned int)&v32, v17, 10, (__int64)SrvAdminReferenceShare);
      *(_QWORD *)(v8 + 72) = v20;
      if ( v20 )
      {
        v23 = RfsTable64Create(v21, (unsigned int)v30, v22, 6, (__int64)SrvAdminReferenceSession);
        *(_QWORD *)(v8 + 80) = v23;
        if ( v23 )
        {
          v26 = RfsTable64Create(v24, (unsigned int)v31, v25, 35, (__int64)SrvAdminReferenceSession);
          *(_QWORD *)(v8 + 88) = v26;
          if ( v26 )
          {
            RtlInitializeGenericTableAvl(
              (PRTL_AVL_TABLE)(v8 + 408),
              (PRTL_AVL_COMPARE_ROUTINE)SrvAdminShareTableCompare,
              SrvAdminShareTableAllocate,
              SrvAdminShareTableFree,
              0);
            ExInitializeResourceLite((PERESOURCE)(v8 + 96));
            ExInitializeResourceLite((PERESOURCE)(v8 + 200));
            ExInitializeResourceLite((PERESOURCE)(v8 + 304));
            v27 = *(_BYTE *)(v8 + 16) == 0;
            *(_BYTE *)(v8 + 520) = 1;
            *(_DWORD *)(v8 + 20) = 219;
            if ( v27 )
            {
              *(_DWORD *)(v8 + 512) = SrvAdminValidateShareScope;
              *(_DWORD *)(v8 + 516) = SrvAdminValidateShareScopeNotAliased;
            }
            else
            {
              *(_QWORD *)(v8 + 512) = 0;
            }
            v28 = (__int64 *)qword_140036C18;
            if ( *(__int64 **)qword_140036C18 != &SrvAdminInstanceList )
              __fastfail(3u);
            *(_QWORD *)v8 = &SrvAdminInstanceList;
            *(_QWORD *)(v8 + 8) = v28;
            *v28 = v8;
            qword_140036C18 = v8;
            _InterlockedIncrement((volatile signed __int32 *)(v8 + 24));
            *a2 = v8;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_Zq(
                WPP_GLOBAL_Control->AttachedDevice,
                18,
                (unsigned int)WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids,
                (_DWORD)v5,
                v8);
            }
            return 0;
          }
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_34;
          }
          v19 = 16;
        }
        else
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_34;
          }
          v19 = 15;
        }
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_34;
        }
        v19 = 14;
      }
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_34;
      }
      v19 = 13;
    }
    WPP_SF_Z(v18->AttachedDevice, v19, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, v5);
LABEL_34:
    v9 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_Zd(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        (unsigned int)WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids,
        (_DWORD)v5,
        154);
    }
    SrvAdminDereferenceInstance(v8);
    *a2 = 0;
    return v9;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, a1);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140024bb8  mov     [rsp-28h+arg_0], rbx
0x140024bbd  mov     [rsp-28h+arg_8], rsi
0x140024bc2  push    rbp
0x140024bc3  push    rdi
0x140024bc4  push    r12
0x140024bc6  push    r14
0x140024bc8  push    r15
0x140024bca  mov     rbp, rsp
0x140024bcd  sub     rsp, 60h
0x140024bd1  mov     eax, 8
0x140024bd6  mov     r8d, ecx
0x140024bd9  mov     [rbp+var_30], eax
0x140024bdc  mov     r12, rdx
0x140024bdf  mov     [rbp+var_2C], eax
0x140024be2  mov     [rbp+var_28], eax
0x140024be5  mov     [rbp+var_1C], eax
0x140024be8  lea     ecx, [rax+2]
0x140024beb  mov     [rbp+var_18], eax
0x140024bee  lea     eax, [rcx-1]
0x140024bf1  mov     [rbp+var_10], eax
0x140024bf4  mov     [rbp+var_C], eax
0x140024bf7  mov     [rbp+var_8], eax
0x140024bfa  mov     [rbp+arg_10], ecx
0x140024bfd  mov     [rbp+arg_14], ecx
0x140024c00  mov     [rbp+var_20], ecx
0x140024c03  cmp     r8d, 6
0x140024c07  jb      short loc_140024C4B
0x140024c09  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024c10  lea     rsi, WPP_GLOBAL_Control
0x140024c17  cmp     rcx, rsi
0x140024c1a  jz      short loc_140024C41
0x140024c1c  mov     eax, [rcx+2Ch]
0x140024c1f  test    al, 20h
0x140024c21  jz      short loc_140024C41
0x140024c23  cmp     byte ptr [rcx+29h], 1
0x140024c27  jb      short loc_140024C41
0x140024c29  mov     rcx, [rcx+18h]
0x140024c2d  mov     r9d, r8d
0x140024c30  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140024c37  mov     edx, 0Bh
0x140024c3c  call    WPP_SF_d
0x140024c41  mov     eax, 0C000000Dh
0x140024c46  jmp     loc_140025007
0x140024c4b  imul    rsi, r8, 38h ; '8'
0x140024c4f  lea     rax, SrvAdminInstanceNames
0x140024c56  mov     r8d, 64614153h
0x140024c5c  lea     r14, [rax+8]
0x140024c60  add     r14, rsi
0x140024c63  lea     r15, [rsi+rax]
0x140024c67  movzx   ecx, word ptr [r15+28h]
0x140024c6c  movzx   edx, word ptr [r14]
0x140024c70  add     rcx, 218h
0x140024c77  add     rdx, rcx
0x140024c7a  mov     ecx, 40h ; '@'
0x140024c7f  call    SrvNetAllocatePoolWithTag
0x140024c84  mov     rdi, rax
0x140024c87  test    rax, rax
0x140024c8a  jnz     short loc_140024CCC
0x140024c8c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024c93  lea     rsi, WPP_GLOBAL_Control
0x140024c9a  cmp     rcx, rsi
0x140024c9d  jz      short loc_140024CC2
0x140024c9f  mov     eax, [rcx+2Ch]
0x140024ca2  test    al, 20h
0x140024ca4  jz      short loc_140024CC2
0x140024ca6  cmp     byte ptr [rcx+29h], 1
0x140024caa  jb      short loc_140024CC2
0x140024cac  mov     rcx, [rcx+18h]
0x140024cb0  lea     edx, [rdi+0Ch]
0x140024cb3  mov     r9, r14
0x140024cb6  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140024cbd  call    WPP_SF_Z
0x140024cc2  mov     ebx, 0C000009Ah
0x140024cc7  jmp     loc_140025005
0x140024ccc  movzx   r8d, word ptr [r14]
0x140024cd0  lea     rcx, [rax+20h]; DestinationString
0x140024cd4  mov     [rax+22h], r8w
0x140024cd9  mov     rdx, r14; SourceString
0x140024cdc  add     rax, 210h
0x140024ce2  mov     [rcx], r8w
0x140024ce6  mov     [rdi+28h], rax
0x140024cea  movzx   eax, word ptr [r15+28h]
0x140024cef  mov     [rdi+32h], ax
0x140024cf3  mov     [rdi+30h], ax
0x140024cf7  lea     rax, [r8+108h]
0x140024cfe  lea     r8, [rdi+rax*2]
0x140024d02  mov     [rdi+38h], r8
0x140024d06  call    cs:__imp_RtlCopyUnicodeString
0x140024d0d  nop     dword ptr [rax+rax+00h]
0x140024d12  lea     rdx, [r15+28h]; SourceString
0x140024d16  lea     rcx, [rdi+30h]; DestinationString
0x140024d1a  call    cs:__imp_RtlCopyUnicodeString
0x140024d21  nop     dword ptr [rax+rax+00h]
0x140024d26  lea     rax, SrvAdminInstanceNames
0x140024d2d  mov     dword ptr [rdi+18h], 1
0x140024d34  mov     dword ptr [rdi+1Ch], 1
0x140024d3b  lea     rdx, [rbp+var_30]
0x140024d3f  mov     al, [rsi+rax]
0x140024d42  mov     r9d, 8
0x140024d48  mov     [rdi+10h], al
0x140024d4b  lea     rax, SrvAdminReferenceSession
0x140024d52  mov     [rsp+60h+TableContext], rax
0x140024d57  call    RfsTable64Create
0x140024d5c  mov     [rdi+40h], rax
0x140024d60  test    rax, rax
0x140024d63  jnz     short loc_140024D9B
0x140024d65  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024d6c  lea     rsi, WPP_GLOBAL_Control
0x140024d73  cmp     rcx, rsi
0x140024d76  jz      loc_140024EA0
0x140024d7c  mov     eax, [rcx+2Ch]
0x140024d7f  test    al, 20h
0x140024d81  jz      loc_140024EA0
0x140024d87  cmp     byte ptr [rcx+29h], 1
0x140024d8b  jb      loc_140024EA0
0x140024d91  mov     edx, 0Dh
0x140024d96  jmp     loc_140024E8D
0x140024d9b  lea     rax, SrvAdminReferenceShare
0x140024da2  mov     r9d, 0Ah
0x140024da8  lea     rdx, [rbp+arg_10]
0x140024dac  mov     [rsp+60h+TableContext], rax
0x140024db1  call    RfsTableCreate
0x140024db6  mov     [rdi+48h], rax
0x140024dba  test    rax, rax
0x140024dbd  jnz     short loc_140024DF5
0x140024dbf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024dc6  lea     rsi, WPP_GLOBAL_Control
0x140024dcd  cmp     rcx, rsi
0x140024dd0  jz      loc_140024EA0
0x140024dd6  mov     eax, [rcx+2Ch]
0x140024dd9  test    al, 20h
0x140024ddb  jz      loc_140024EA0
0x140024de1  cmp     byte ptr [rcx+29h], 1
0x140024de5  jb      loc_140024EA0
0x140024deb  mov     edx, 0Eh
0x140024df0  jmp     loc_140024E8D
0x140024df5  lea     rax, SrvAdminReferenceSession
0x140024dfc  mov     r9d, 6
0x140024e02  lea     rdx, [rbp+var_20]
0x140024e06  mov     [rsp+60h+TableContext], rax
0x140024e0b  call    RfsTable64Create
0x140024e10  mov     [rdi+50h], rax
0x140024e14  test    rax, rax
0x140024e17  jnz     short loc_140024E40
0x140024e19  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024e20  lea     rsi, WPP_GLOBAL_Control
0x140024e27  cmp     rcx, rsi
0x140024e2a  jz      short loc_140024EA0
0x140024e2c  mov     eax, [rcx+2Ch]
0x140024e2f  test    al, 20h
0x140024e31  jz      short loc_140024EA0
0x140024e33  cmp     byte ptr [rcx+29h], 1
0x140024e37  jb      short loc_140024EA0
0x140024e39  mov     edx, 0Fh
0x140024e3e  jmp     short loc_140024E8D
0x140024e40  lea     rax, SrvAdminReferenceSession
0x140024e47  mov     r9d, 23h ; '#'
0x140024e4d  lea     rdx, [rbp+var_10]
0x140024e51  mov     [rsp+60h+TableContext], rax
0x140024e56  call    RfsTable64Create
0x140024e5b  mov     [rdi+58h], rax
0x140024e5f  test    rax, rax
0x140024e62  jnz     loc_140024EF3
0x140024e68  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024e6f  lea     rsi, WPP_GLOBAL_Control
0x140024e76  cmp     rcx, rsi
0x140024e79  jz      short loc_140024EA0
0x140024e7b  mov     eax, [rcx+2Ch]
0x140024e7e  test    al, 20h
0x140024e80  jz      short loc_140024EA0
0x140024e82  cmp     byte ptr [rcx+29h], 1
0x140024e86  jb      short loc_140024EA0
0x140024e88  mov     edx, 10h
0x140024e8d  mov     rcx, [rcx+18h]
0x140024e91  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140024e98  mov     r9, r14
0x140024e9b  call    WPP_SF_Z
0x140024ea0  mov     ebx, 0C000009Ah
0x140024ea5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024eac  cmp     rcx, rsi
0x140024eaf  jz      short loc_140024EDE
0x140024eb1  mov     eax, [rcx+2Ch]
0x140024eb4  test    al, 20h
0x140024eb6  jz      short loc_140024EDE
0x140024eb8  cmp     byte ptr [rcx+29h], 1
0x140024ebc  jb      short loc_140024EDE
0x140024ebe  mov     rcx, [rcx+18h]
0x140024ec2  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140024ec9  mov     edx, 13h
0x140024ece  mov     dword ptr [rsp+60h+TableContext], 0C000009Ah
0x140024ed6  mov     r9, r14
0x140024ed9  call    WPP_SF_Zd
0x140024ede  mov     rcx, rdi
0x140024ee1  call    SrvAdminDereferenceInstance
0x140024ee6  mov     qword ptr [r12], 0
0x140024eee  jmp     loc_140025005
0x140024ef3  lea     rcx, [rdi+198h]; Table
0x140024efa  mov     [rsp+60h+TableContext], 0; TableContext
0x140024f03  lea     r9, SrvAdminShareTableFree; FreeRoutine
0x140024f0a  lea     r8, SrvAdminShareTableAllocate; AllocateRoutine
0x140024f11  lea     rdx, SrvAdminShareTableCompare; CompareRoutine
0x140024f18  call    cs:__imp_RtlInitializeGenericTableAvl
0x140024f1f  nop     dword ptr [rax+rax+00h]
0x140024f24  lea     rcx, [rdi+60h]; Resource
0x140024f28  call    cs:__imp_ExInitializeResourceLite
0x140024f2f  nop     dword ptr [rax+rax+00h]
0x140024f34  lea     rcx, [rdi+0C8h]; Resource
0x140024f3b  call    cs:__imp_ExInitializeResourceLite
0x140024f42  nop     dword ptr [rax+rax+00h]
0x140024f47  lea     rcx, [rdi+130h]; Resource
0x140024f4e  call    cs:__imp_ExInitializeResourceLite
0x140024f55  nop     dword ptr [rax+rax+00h]
0x140024f5a  cmp     byte ptr [rdi+10h], 0
0x140024f5e  mov     byte ptr [rdi+208h], 1
0x140024f65  mov     dword ptr [rdi+14h], 0DBh
0x140024f6c  jnz     short loc_140024F88
0x140024f6e  mov     eax, cs:SrvAdminValidateShareScope
0x140024f74  mov     [rdi+200h], eax
0x140024f7a  mov     eax, cs:SrvAdminValidateShareScopeNotAliased
0x140024f80  mov     [rdi+204h], eax
0x140024f86  jmp     short loc_140024F93
0x140024f88  mov     qword ptr [rdi+200h], 0
0x140024f93  mov     rax, cs:qword_140036C18
0x140024f9a  lea     rcx, SrvAdminInstanceList
0x140024fa1  cmp     [rax], rcx
0x140024fa4  jz      short loc_140024FAD
0x140024fa6  mov     ecx, 3
0x140024fab  int     29h; Win8: RtlFailFast(ecx)
0x140024fad  mov     [rdi], rcx
0x140024fb0  mov     [rdi+8], rax
0x140024fb4  mov     [rax], rdi
0x140024fb7  mov     cs:qword_140036C18, rdi
0x140024fbe  lock inc dword ptr [rdi+18h]
0x140024fc2  mov     [r12], rdi
0x140024fc6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024fcd  lea     rsi, WPP_GLOBAL_Control
0x140024fd4  cmp     rcx, rsi
0x140024fd7  jz      short loc_140025003
0x140024fd9  mov     eax, [rcx+2Ch]
0x140024fdc  test    al, 20h
0x140024fde  jz      short loc_140025003
0x140024fe0  cmp     byte ptr [rcx+29h], 2
0x140024fe4  jb      short loc_140025003
0x140024fe6  mov     rcx, [rcx+18h]
0x140024fea  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140024ff1  mov     edx, 12h
0x140024ff6  mov     [rsp+60h+TableContext], rdi
0x140024ffb  mov     r9, r14
0x140024ffe  call    WPP_SF_Zq
0x140025003  xor     ebx, ebx
0x140025005  mov     eax, ebx
0x140025007  lea     r11, [rsp+60h+var_s0]
0x14002500c  mov     rbx, [r11+30h]
0x140025010  mov     rsi, [r11+38h]
0x140025014  mov     rsp, r11
0x140025017  pop     r15
0x140025019  pop     r14
0x14002501b  pop     r12
0x14002501d  pop     rdi
0x14002501e  pop     rbp
0x14002501f  retn
```
