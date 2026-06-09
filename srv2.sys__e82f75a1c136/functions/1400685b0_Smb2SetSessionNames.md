# Smb2SetSessionNames

- ea: `0x1400685b0`
- end: `0x140068832`
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
- `0x1400685b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006874c`
- `ntoskrnl!ExAllocatePool2` at `0x14006874c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400685ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400685ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068660`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400687ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068660`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400687ed`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140068618`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140068640`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140068618`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140068640`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006871d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006871d`
- `srvnet!SrvNetSetConnectionServerName` at `0x1400686a7`
- `srvnet!SrvNetSetConnectionServerName` at `0x1400686a7`
- `srvnet!SrvAdminSetSessionName` at `0x140068811`
- `srvnet!SrvAdminSetSessionName` at `0x140068811`

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
0x1400685b0  push    rbx
0x1400685b2  push    rbp
0x1400685b3  push    rsi
0x1400685b4  push    rdi
0x1400685b5  push    r12
0x1400685b7  push    r13
0x1400685b9  push    r14
0x1400685bb  push    r15
0x1400685bd  sub     rsp, 48h
0x1400685c1  cmp     word ptr [rdx], 20h ; ' '
0x1400685c5  mov     bpl, r9b
0x1400685c8  mov     r14, r8
0x1400685cb  mov     rsi, rdx
0x1400685ce  mov     rbx, rcx
0x1400685d1  jbe     short loc_1400685DD
0x1400685d3  mov     eax, 0C000000Dh
0x1400685d8  jmp     loc_140068820
0x1400685dd  mov     rcx, [rcx+18h]
0x1400685e1  xor     r13d, r13d
0x1400685e4  add     rcx, 50h ; 'P'
0x1400685e8  xor     edx, edx
0x1400685ea  mov     r15d, r13d
0x1400685ed  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400685f4  nop     dword ptr [rax+rax+00h]
0x1400685f9  test    bpl, bpl
0x1400685fc  jz      short loc_140068605
0x1400685fe  mov     [rbx+11Eh], bpl
0x140068605  mov     rcx, [rbx+0B8h]; String1
0x14006860c  cmp     [rcx], r13w
0x140068610  jz      short loc_140068671
0x140068612  mov     r8b, 1; CaseInSensitive
0x140068615  mov     rdx, rsi; String2
0x140068618  call    cs:__imp_RtlEqualUnicodeString
0x14006861f  nop     dword ptr [rax+rax+00h]
0x140068624  test    al, al
0x140068626  jz      short loc_140068650
0x140068628  mov     rcx, [rbx+0C0h]; String1
0x14006862f  test    rcx, rcx
0x140068632  jz      short loc_140068650
0x140068634  cmp     [rcx], r13w
0x140068638  jz      short loc_140068650
0x14006863a  mov     r8b, 1; CaseInSensitive
0x14006863d  mov     rdx, r14; String2
0x140068640  call    cs:__imp_RtlEqualUnicodeString
0x140068647  nop     dword ptr [rax+rax+00h]
0x14006864c  test    al, al
0x14006864e  jnz     short loc_140068656
0x140068650  mov     r15d, 0C00000C9h
0x140068656  mov     rcx, [rbx+18h]
0x14006865a  xor     edx, edx
0x14006865c  add     rcx, 50h ; 'P'
0x140068660  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140068667  nop     dword ptr [rax+rax+00h]
0x14006866c  jmp     loc_14006881D
0x140068671  lea     r12, [rbx+78h]
0x140068675  mov     [rsp+88h+arg_8], r13b
0x14006867d  mov     rdi, [r12]
0x140068681  cmp     rdi, r12
0x140068684  jz      loc_140068713
0x14006868a  lea     r15, WPP_GLOBAL_Control
0x140068691  mov     rcx, [rdi+20h]
0x140068695  lea     r8, [rsp+88h+arg_8]
0x14006869d  mov     rdx, rsi
0x1400686a0  mov     rcx, [rcx+1E0h]
0x1400686a7  call    cs:__imp_SrvNetSetConnectionServerName
0x1400686ae  nop     dword ptr [rax+rax+00h]
0x1400686b3  test    eax, eax
0x1400686b5  jns     short loc_1400686F5
0x1400686b7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400686be  cmp     rcx, r15
0x1400686c1  jz      short loc_1400686F5
0x1400686c3  test    dword ptr [rcx+2Ch], 80000h
0x1400686ca  jz      short loc_1400686F5
0x1400686cc  cmp     byte ptr [rcx+29h], 1
0x1400686d0  jb      short loc_1400686F5
0x1400686d2  mov     r9, [rdi+20h]
0x1400686d6  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x1400686dd  mov     rcx, [rcx+18h]
0x1400686e1  mov     edx, 10h
0x1400686e6  mov     [rsp+88h+var_60], rbx
0x1400686eb  mov     [rsp+88h+var_68], rsi
0x1400686f0  call    WPP_SF_qZq
0x1400686f5  test    bpl, bpl
0x1400686f8  jz      short loc_140068708
0x1400686fa  mov     rcx, [rdi+20h]
0x1400686fe  mov     edx, 2
0x140068703  call    Smb2SetConnectionKeepalive
0x140068708  mov     rdi, [rdi]
0x14006870b  cmp     rdi, r12
0x14006870e  jnz     short loc_140068691
0x140068710  mov     r15d, r13d
0x140068713  mov     rcx, [rbx+0B8h]; DestinationString
0x14006871a  mov     rdx, rsi; SourceString
0x14006871d  call    cs:__imp_RtlCopyUnicodeString
0x140068724  nop     dword ptr [rax+rax+00h]
0x140068729  mov     rdx, [rbx+0C0h]
0x140068730  test    rdx, rdx
0x140068733  jnz     short loc_1400687AB
0x140068735  movzx   edx, word ptr [r14]
0x140068739  mov     ecx, 42h ; 'B'
0x14006873e  add     rdx, 11h
0x140068742  mov     r8d, 7332534Ch
0x140068748  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14006874c  call    cs:__imp_ExAllocatePool2
0x140068753  nop     dword ptr [rax+rax+00h]
0x140068758  mov     [rbx+0C0h], rax
0x14006875f  test    rax, rax
0x140068762  jz      short loc_1400687A3
0x140068764  movzx   ecx, word ptr [r14]
0x140068768  mov     [rax+2], cx
0x14006876c  mov     rcx, [rbx+0C0h]
0x140068773  movzx   eax, word ptr [rcx+2]
0x140068777  mov     [rcx], ax
0x14006877a  mov     rcx, [rbx+0C0h]
0x140068781  lea     rax, [rcx+10h]
0x140068785  mov     [rcx+8], rax
0x140068789  mov     rcx, [rbx+0C0h]
0x140068790  movzx   r8d, word ptr [r14]; Size
0x140068794  mov     rdx, [r14+8]; Src
0x140068798  mov     rcx, [rcx+8]; void *
0x14006879c  call    memmove
0x1400687a1  jmp     short loc_1400687E3
0x1400687a3  mov     r15d, 0C000009Ah
0x1400687a9  jmp     short loc_1400687E3
0x1400687ab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400687b2  lea     rax, WPP_GLOBAL_Control
0x1400687b9  cmp     rcx, rax
0x1400687bc  jz      short loc_1400687E3
0x1400687be  test    dword ptr [rcx+2Ch], 80000h
0x1400687c5  jz      short loc_1400687E3
0x1400687c7  cmp     byte ptr [rcx+29h], 1
0x1400687cb  jb      short loc_1400687E3
0x1400687cd  mov     rcx, [rcx+18h]
0x1400687d1  mov     r9, r14
0x1400687d4  mov     [rsp+88h+var_60], rdx
0x1400687d9  mov     [rsp+88h+var_68], rbx
0x1400687de  call    WPP_SF_ZqZ
0x1400687e3  mov     rcx, [rbx+18h]
0x1400687e7  xor     edx, edx
0x1400687e9  add     rcx, 50h ; 'P'
0x1400687ed  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400687f4  nop     dword ptr [rax+rax+00h]
0x1400687f9  mov     rcx, [rbx+138h]
0x140068800  mov     r8, rsi
0x140068803  mov     rdx, [rbx+40h]
0x140068807  movzx   r9d, byte ptr [rcx]
0x14006880b  mov     ecx, cs:Smb2ProviderId
0x140068811  call    cs:__imp_SrvAdminSetSessionName
0x140068818  nop     dword ptr [rax+rax+00h]
0x14006881d  mov     eax, r15d
0x140068820  add     rsp, 48h
0x140068824  pop     r15
0x140068826  pop     r14
0x140068828  pop     r13
0x14006882a  pop     r12
0x14006882c  pop     rdi
0x14006882d  pop     rsi
0x14006882e  pop     rbp
0x14006882f  pop     rbx
0x140068830  retn
```
