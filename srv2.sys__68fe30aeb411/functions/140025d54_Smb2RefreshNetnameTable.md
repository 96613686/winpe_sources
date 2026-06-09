# Smb2RefreshNetnameTable

- ea: `0x140025d54`
- end: `0x140025f65`
- name: `Smb2RefreshNetnameTable`
- size: `529`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14007667c`

## callees

- `0x14000c520`
- `0x140010af8`
- `0x140011580`
- `0x1400139d0`
- `0x14001891c`
- `0x14002578c`
- `0x140025d54`
- `0x140038560`
- `0x140038680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140025d89`
- `ntoskrnl!ExAllocatePool2` at `0x140025d89`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025f37`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025f37`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025e58`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025e58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e3a`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140025de5`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140025de5`
- `srvnet!SrvNetNotifyClientsUpdateNetname` at `0x140025f47`
- `srvnet!SrvNetNotifyClientsUpdateNetname` at `0x140025f47`

## pseudocode

```c
__int64 __fastcall Smb2RefreshNetnameTable(void *Src, size_t Size, __int64 a3)
{
  size_t v3; // rdi
  __int64 Pool2; // rax
  __int64 v8; // rbx
  UNICODE_STRING *v9; // rbp
  char v10; // si
  __int64 v11; // rax
  NTSTATUS v12; // edi
  int v13; // r15d
  __int64 v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // r14d

  v3 = (unsigned int)Size;
  if ( (int)Size + 24 < (unsigned int)Size )
    return 3221225621LL;
  Pool2 = ExAllocatePool2(66, (unsigned int)(Size + 24), 1852724044);
  v8 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v9 = (UNICODE_STRING *)(Pool2 + 24);
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  v10 = 1;
  *(_DWORD *)(Pool2 + 16) = 1;
  memmove((void *)(Pool2 + 24), Src, v3);
  v11 = *(_QWORD *)(v8 + 32);
  if ( v11 )
    *(_QWORD *)(v8 + 32) = v8 + v11 + 24;
  v12 = RtlUpcaseUnicodeString(v9, v9, 0);
  if ( v12 >= 0 )
  {
    v13 = 0;
    ExAcquireResourceExclusiveLite(&Smb2NameLock, 1u);
    v14 = RfsHashTableLookup(Smb2NetnameTable, *(_QWORD *)(v8 + 32), v9->Length);
    if ( v14 )
    {
      v15 = *(_DWORD *)(v8 + 44);
      if ( v15 == *(_DWORD *)(v14 + 44) && !memcmp((const void *)(v8 + 48), (const void *)(v14 + 48), v15) )
      {
        Smb2DereferenceNetname(v14);
        v12 = 0;
LABEL_23:
        Smb2DereferenceNetname(v8);
LABEL_24:
        ExReleaseResourceLite(&Smb2NameLock);
        if ( v12 >= 0 )
          SrvNetNotifyClientsUpdateNetname();
        return (unsigned int)v12;
      }
      RfsHashTableRemove(Smb2NetnameTable, v14, *(_QWORD *)(v8 + 32), v9->Length);
      Smb2DereferenceNetname(v14);
      Smb2DereferenceNetname(v14);
      v13 = 1;
    }
    if ( (*(_DWORD *)(v8 + 40) & 1) != 0 )
    {
      v16 = v13 == 1;
      v12 = RfsHashTableInsertEx((_DWORD)Smb2NetnameTable, v8, *(_QWORD *)(v8 + 32), v9->Length, 0);
      if ( v12 < 0 )
        goto LABEL_23;
      v10 = 0;
    }
    else
    {
      v16 = 2;
    }
    Smb2LogNetNameChange(v8, v16, a3);
    if ( !v10 )
      goto LABEL_24;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_Zd(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        (unsigned int)WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
        (_DWORD)v9,
        v12);
  }
  ExFreePoolWithTag((PVOID)v8, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140025d54  push    rbx
0x140025d56  push    rbp
0x140025d57  push    rsi
0x140025d58  push    rdi
0x140025d59  push    r12
0x140025d5b  push    r14
0x140025d5d  push    r15
0x140025d5f  sub     rsp, 30h
0x140025d63  mov     edi, edx
0x140025d65  mov     r12, r8
0x140025d68  mov     r14, rcx
0x140025d6b  lea     eax, [rdi+18h]
0x140025d6e  cmp     eax, edx
0x140025d70  jnb     short loc_140025D7C
0x140025d72  mov     eax, 0C0000095h
0x140025d77  jmp     loc_140025F55
0x140025d7c  mov     edx, eax
0x140025d7e  mov     ecx, 42h ; 'B'
0x140025d83  mov     r8d, 6E6E534Ch
0x140025d89  call    cs:__imp_ExAllocatePool2
0x140025d90  nop     dword ptr [rax+rax+00h]
0x140025d95  mov     rbx, rax
0x140025d98  test    rax, rax
0x140025d9b  jnz     short loc_140025DA7
0x140025d9d  mov     eax, 0C000009Ah
0x140025da2  jmp     loc_140025F55
0x140025da7  lea     rbp, [rax+18h]
0x140025dab  mov     [rax+8], rbx
0x140025daf  mov     [rax], rbx
0x140025db2  mov     esi, 1
0x140025db7  mov     rcx, rbp; void *
0x140025dba  mov     [rax+10h], esi
0x140025dbd  mov     r8, rdi; Size
0x140025dc0  mov     rdx, r14; Src
0x140025dc3  call    memmove
0x140025dc8  mov     rax, [rbx+20h]
0x140025dcc  test    rax, rax
0x140025dcf  jz      short loc_140025DDC
0x140025dd1  add     rax, 18h
0x140025dd5  add     rax, rbx
0x140025dd8  mov     [rbx+20h], rax
0x140025ddc  xor     r8d, r8d; AllocateDestinationString
0x140025ddf  mov     rdx, rbp; SourceString
0x140025de2  mov     rcx, rbp; DestinationString
0x140025de5  call    cs:__imp_RtlUpcaseUnicodeString
0x140025dec  nop     dword ptr [rax+rax+00h]
0x140025df1  mov     edi, eax
0x140025df3  test    eax, eax
0x140025df5  jns     short loc_140025E4B
0x140025df7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025dfe  lea     rax, WPP_GLOBAL_Control
0x140025e05  cmp     rcx, rax
0x140025e08  jz      short loc_140025E35
0x140025e0a  test    dword ptr [rcx+2Ch], 4000h
0x140025e11  jz      short loc_140025E35
0x140025e13  cmp     [rcx+29h], sil
0x140025e17  jb      short loc_140025E35
0x140025e19  mov     rcx, [rcx+18h]
0x140025e1d  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x140025e24  mov     edx, 25h ; '%'
0x140025e29  mov     [rsp+68h+var_48], edi
0x140025e2d  mov     r9, rbp
0x140025e30  call    WPP_SF_Zd
0x140025e35  xor     edx, edx; Tag
0x140025e37  mov     rcx, rbx; P
0x140025e3a  call    cs:__imp_ExFreePoolWithTag
0x140025e41  nop     dword ptr [rax+rax+00h]
0x140025e46  jmp     loc_140025F53
0x140025e4b  mov     dl, sil; Wait
0x140025e4e  lea     rcx, Smb2NameLock; Resource
0x140025e55  xor     r15d, r15d
0x140025e58  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140025e5f  nop     dword ptr [rax+rax+00h]
0x140025e64  movzx   r8d, word ptr [rbp+0]
0x140025e69  mov     rdx, [rbx+20h]
0x140025e6d  mov     rcx, cs:Smb2NetnameTable
0x140025e74  call    RfsHashTableLookup
0x140025e79  mov     r14, rax
0x140025e7c  test    rax, rax
0x140025e7f  jz      short loc_140025ED5
0x140025e81  mov     eax, [rbx+2Ch]
0x140025e84  cmp     eax, [r14+2Ch]
0x140025e88  jnz     short loc_140025EAA
0x140025e8a  mov     r8d, eax; Size
0x140025e8d  lea     rdx, [r14+30h]; Buf2
0x140025e91  lea     rcx, [rbx+30h]; Buf1
0x140025e95  call    memcmp
0x140025e9a  test    eax, eax
0x140025e9c  jnz     short loc_140025EAA
0x140025e9e  mov     rcx, r14
0x140025ea1  call    Smb2DereferenceNetname
0x140025ea6  xor     edi, edi
0x140025ea8  jmp     short loc_140025F28
0x140025eaa  movzx   r9d, word ptr [rbp+0]
0x140025eaf  mov     rdx, r14
0x140025eb2  mov     r8, [rbx+20h]
0x140025eb6  mov     rcx, cs:Smb2NetnameTable
0x140025ebd  call    RfsHashTableRemove
0x140025ec2  mov     rcx, r14
0x140025ec5  call    Smb2DereferenceNetname
0x140025eca  mov     rcx, r14
0x140025ecd  call    Smb2DereferenceNetname
0x140025ed2  mov     r15d, esi
0x140025ed5  mov     eax, [rbx+28h]
0x140025ed8  test    sil, al
0x140025edb  jz      short loc_140025F0F
0x140025edd  movzx   r9d, word ptr [rbp+0]
0x140025ee2  xor     r14d, r14d
0x140025ee5  mov     r8, [rbx+20h]
0x140025ee9  cmp     r15d, esi
0x140025eec  mov     rcx, cs:Smb2NetnameTable
0x140025ef3  mov     rdx, rbx
0x140025ef6  cmovz   r14d, r15d
0x140025efa  mov     byte ptr [rsp+68h+var_48], 0
0x140025eff  call    RfsHashTableInsertEx
0x140025f04  mov     edi, eax
0x140025f06  test    eax, eax
0x140025f08  js      short loc_140025F28
0x140025f0a  xor     sil, sil
0x140025f0d  jmp     short loc_140025F15
0x140025f0f  mov     r14d, 2
0x140025f15  mov     r8, r12
0x140025f18  mov     edx, r14d
0x140025f1b  mov     rcx, rbx
0x140025f1e  call    Smb2LogNetNameChange
0x140025f23  test    sil, sil
0x140025f26  jz      short loc_140025F30
0x140025f28  mov     rcx, rbx
0x140025f2b  call    Smb2DereferenceNetname
0x140025f30  lea     rcx, Smb2NameLock; Resource
0x140025f37  call    cs:__imp_ExReleaseResourceLite
0x140025f3e  nop     dword ptr [rax+rax+00h]
0x140025f43  test    edi, edi
0x140025f45  js      short loc_140025F53
0x140025f47  call    cs:__imp_SrvNetNotifyClientsUpdateNetname
0x140025f4e  nop     dword ptr [rax+rax+00h]
0x140025f53  mov     eax, edi
0x140025f55  add     rsp, 30h
0x140025f59  pop     r15
0x140025f5b  pop     r14
0x140025f5d  pop     r12
0x140025f5f  pop     rdi
0x140025f60  pop     rsi
0x140025f61  pop     rbp
0x140025f62  pop     rbx
0x140025f63  retn
```
