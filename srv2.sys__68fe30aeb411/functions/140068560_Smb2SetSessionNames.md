# Smb2SetSessionNames

- ea: `0x140068560`
- end: `0x1400687e2`
- name: `Smb2SetSessionNames`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14008b4f0`

## callees

- `0x14001beac`
- `0x140024144`
- `0x140030160`
- `0x140038680`
- `0x140068560`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400686fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400686fc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006859d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006859d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068610`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006879d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068610`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006879d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400685c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400685f0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400685c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400685f0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400686cd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400686cd`
- `srvnet!SrvNetSetConnectionServerName` at `0x140068657`
- `srvnet!SrvNetSetConnectionServerName` at `0x140068657`
- `srvnet!SrvAdminSetSessionName` at `0x1400687c1`
- `srvnet!SrvAdminSetSessionName` at `0x1400687c1`

## pseudocode

```c
__int64 __fastcall Smb2SetSessionNames(__int64 a1, const UNICODE_STRING *a2, const UNICODE_STRING *a3, char a4)
{
  unsigned int v9; // r15d
  const UNICODE_STRING *v10; // rcx
  const UNICODE_STRING *v11; // rcx
  _QWORD *v12; // rdi
  int v13; // r8d
  __int64 v14; // rdx
  __int64 Pool2; // rax
  char v16; // [rsp+98h] [rbp+10h] BYREF

  if ( a2->Length > 0x20u )
    return 3221225485LL;
  v9 = 0;
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a1 + 24) + 80LL, 0);
  if ( a4 )
    *(_BYTE *)(a1 + 286) = a4;
  v10 = *(const UNICODE_STRING **)(a1 + 184);
  if ( v10->Length )
  {
    if ( !RtlEqualUnicodeString(v10, a2, 1u)
      || (v11 = *(const UNICODE_STRING **)(a1 + 192)) == 0
      || !v11->Length
      || !RtlEqualUnicodeString(v11, a3, 1u) )
    {
      v9 = -1073741623;
    }
    ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 24) + 80LL, 0);
  }
  else
  {
    v16 = 0;
    v12 = *(_QWORD **)(a1 + 120);
    if ( v12 != (_QWORD *)(a1 + 120) )
    {
      do
      {
        if ( (int)SrvNetSetConnectionServerName(*(_QWORD *)(v12[4] + 480LL), a2, &v16) < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZq(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            (unsigned int)WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids,
            v12[4],
            (__int64)a2,
            a1);
        }
        if ( a4 )
          Smb2SetConnectionKeepalive(v12[4], 2);
        v12 = (_QWORD *)*v12;
      }
      while ( v12 != (_QWORD *)(a1 + 120) );
      v9 = 0;
    }
    RtlCopyUnicodeString(*(PUNICODE_STRING *)(a1 + 184), a2);
    v14 = *(_QWORD *)(a1 + 192);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_ZqZ(WPP_GLOBAL_Control->AttachedDevice, v14, v13, (_DWORD)a3, a1, *(_QWORD *)(a1 + 192));
      }
    }
    else
    {
      Pool2 = ExAllocatePool2(66, (a3->Length + 17LL) & 0xFFFFFFFFFFFFFFFEuLL, 1932677964);
      *(_QWORD *)(a1 + 192) = Pool2;
      if ( Pool2 )
      {
        *(_WORD *)(Pool2 + 2) = a3->Length;
        **(_WORD **)(a1 + 192) = *(_WORD *)(*(_QWORD *)(a1 + 192) + 2LL);
        *(_QWORD *)(*(_QWORD *)(a1 + 192) + 8LL) = *(_QWORD *)(a1 + 192) + 16LL;
        memmove(*(void **)(*(_QWORD *)(a1 + 192) + 8LL), a3->Buffer, a3->Length);
      }
      else
      {
        v9 = -1073741670;
      }
    }
    ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 24) + 80LL, 0);
    SrvAdminSetSessionName((unsigned int)Smb2ProviderId, *(_QWORD *)(a1 + 64), a2, **(unsigned __int8 **)(a1 + 312));
  }
  return v9;
}

```

## disassembly

```asm
0x140068560  push    rbx
0x140068562  push    rbp
0x140068563  push    rsi
0x140068564  push    rdi
0x140068565  push    r12
0x140068567  push    r13
0x140068569  push    r14
0x14006856b  push    r15
0x14006856d  sub     rsp, 48h
0x140068571  cmp     word ptr [rdx], 20h ; ' '
0x140068575  mov     bpl, r9b
0x140068578  mov     r14, r8
0x14006857b  mov     rsi, rdx
0x14006857e  mov     rbx, rcx
0x140068581  jbe     short loc_14006858D
0x140068583  mov     eax, 0C000000Dh
0x140068588  jmp     loc_1400687D0
0x14006858d  mov     rcx, [rcx+18h]
0x140068591  xor     r13d, r13d
0x140068594  add     rcx, 50h ; 'P'
0x140068598  xor     edx, edx
0x14006859a  mov     r15d, r13d
0x14006859d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400685a4  nop     dword ptr [rax+rax+00h]
0x1400685a9  test    bpl, bpl
0x1400685ac  jz      short loc_1400685B5
0x1400685ae  mov     [rbx+11Eh], bpl
0x1400685b5  mov     rcx, [rbx+0B8h]; String1
0x1400685bc  cmp     [rcx], r13w
0x1400685c0  jz      short loc_140068621
0x1400685c2  mov     r8b, 1; CaseInSensitive
0x1400685c5  mov     rdx, rsi; String2
0x1400685c8  call    cs:__imp_RtlEqualUnicodeString
0x1400685cf  nop     dword ptr [rax+rax+00h]
0x1400685d4  test    al, al
0x1400685d6  jz      short loc_140068600
0x1400685d8  mov     rcx, [rbx+0C0h]; String1
0x1400685df  test    rcx, rcx
0x1400685e2  jz      short loc_140068600
0x1400685e4  cmp     [rcx], r13w
0x1400685e8  jz      short loc_140068600
0x1400685ea  mov     r8b, 1; CaseInSensitive
0x1400685ed  mov     rdx, r14; String2
0x1400685f0  call    cs:__imp_RtlEqualUnicodeString
0x1400685f7  nop     dword ptr [rax+rax+00h]
0x1400685fc  test    al, al
0x1400685fe  jnz     short loc_140068606
0x140068600  mov     r15d, 0C00000C9h
0x140068606  mov     rcx, [rbx+18h]
0x14006860a  xor     edx, edx
0x14006860c  add     rcx, 50h ; 'P'
0x140068610  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140068617  nop     dword ptr [rax+rax+00h]
0x14006861c  jmp     loc_1400687CD
0x140068621  lea     r12, [rbx+78h]
0x140068625  mov     [rsp+88h+arg_8], r13b
0x14006862d  mov     rdi, [r12]
0x140068631  cmp     rdi, r12
0x140068634  jz      loc_1400686C3
0x14006863a  lea     r15, WPP_GLOBAL_Control
0x140068641  mov     rcx, [rdi+20h]
0x140068645  lea     r8, [rsp+88h+arg_8]
0x14006864d  mov     rdx, rsi
0x140068650  mov     rcx, [rcx+1E0h]
0x140068657  call    cs:__imp_SrvNetSetConnectionServerName
0x14006865e  nop     dword ptr [rax+rax+00h]
0x140068663  test    eax, eax
0x140068665  jns     short loc_1400686A5
0x140068667  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006866e  cmp     rcx, r15
0x140068671  jz      short loc_1400686A5
0x140068673  test    dword ptr [rcx+2Ch], 80000h
0x14006867a  jz      short loc_1400686A5
0x14006867c  cmp     byte ptr [rcx+29h], 1
0x140068680  jb      short loc_1400686A5
0x140068682  mov     r9, [rdi+20h]
0x140068686  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x14006868d  mov     rcx, [rcx+18h]
0x140068691  mov     edx, 10h
0x140068696  mov     [rsp+88h+var_60], rbx
0x14006869b  mov     [rsp+88h+var_68], rsi
0x1400686a0  call    WPP_SF_qZq
0x1400686a5  test    bpl, bpl
0x1400686a8  jz      short loc_1400686B8
0x1400686aa  mov     rcx, [rdi+20h]
0x1400686ae  mov     edx, 2
0x1400686b3  call    Smb2SetConnectionKeepalive
0x1400686b8  mov     rdi, [rdi]
0x1400686bb  cmp     rdi, r12
0x1400686be  jnz     short loc_140068641
0x1400686c0  mov     r15d, r13d
0x1400686c3  mov     rcx, [rbx+0B8h]; DestinationString
0x1400686ca  mov     rdx, rsi; SourceString
0x1400686cd  call    cs:__imp_RtlCopyUnicodeString
0x1400686d4  nop     dword ptr [rax+rax+00h]
0x1400686d9  mov     rdx, [rbx+0C0h]
0x1400686e0  test    rdx, rdx
0x1400686e3  jnz     short loc_14006875B
0x1400686e5  movzx   edx, word ptr [r14]
0x1400686e9  mov     ecx, 42h ; 'B'
0x1400686ee  add     rdx, 11h
0x1400686f2  mov     r8d, 7332534Ch
0x1400686f8  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1400686fc  call    cs:__imp_ExAllocatePool2
0x140068703  nop     dword ptr [rax+rax+00h]
0x140068708  mov     [rbx+0C0h], rax
0x14006870f  test    rax, rax
0x140068712  jz      short loc_140068753
0x140068714  movzx   ecx, word ptr [r14]
0x140068718  mov     [rax+2], cx
0x14006871c  mov     rcx, [rbx+0C0h]
0x140068723  movzx   eax, word ptr [rcx+2]
0x140068727  mov     [rcx], ax
0x14006872a  mov     rcx, [rbx+0C0h]
0x140068731  lea     rax, [rcx+10h]
0x140068735  mov     [rcx+8], rax
0x140068739  mov     rcx, [rbx+0C0h]
0x140068740  movzx   r8d, word ptr [r14]; Size
0x140068744  mov     rdx, [r14+8]; Src
0x140068748  mov     rcx, [rcx+8]; void *
0x14006874c  call    memmove
0x140068751  jmp     short loc_140068793
0x140068753  mov     r15d, 0C000009Ah
0x140068759  jmp     short loc_140068793
0x14006875b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068762  lea     rax, WPP_GLOBAL_Control
0x140068769  cmp     rcx, rax
0x14006876c  jz      short loc_140068793
0x14006876e  test    dword ptr [rcx+2Ch], 80000h
0x140068775  jz      short loc_140068793
0x140068777  cmp     byte ptr [rcx+29h], 1
0x14006877b  jb      short loc_140068793
0x14006877d  mov     rcx, [rcx+18h]
0x140068781  mov     r9, r14
0x140068784  mov     [rsp+88h+var_60], rdx
0x140068789  mov     [rsp+88h+var_68], rbx
0x14006878e  call    WPP_SF_ZqZ
0x140068793  mov     rcx, [rbx+18h]
0x140068797  xor     edx, edx
0x140068799  add     rcx, 50h ; 'P'
0x14006879d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400687a4  nop     dword ptr [rax+rax+00h]
0x1400687a9  mov     rcx, [rbx+138h]
0x1400687b0  mov     r8, rsi
0x1400687b3  mov     rdx, [rbx+40h]
0x1400687b7  movzx   r9d, byte ptr [rcx]
0x1400687bb  mov     ecx, cs:Smb2ProviderId
0x1400687c1  call    cs:__imp_SrvAdminSetSessionName
0x1400687c8  nop     dword ptr [rax+rax+00h]
0x1400687cd  mov     eax, r15d
0x1400687d0  add     rsp, 48h
0x1400687d4  pop     r15
0x1400687d6  pop     r14
0x1400687d8  pop     r13
0x1400687da  pop     r12
0x1400687dc  pop     rdi
0x1400687dd  pop     rsi
0x1400687de  pop     rbp
0x1400687df  pop     rbx
0x1400687e0  retn
```
