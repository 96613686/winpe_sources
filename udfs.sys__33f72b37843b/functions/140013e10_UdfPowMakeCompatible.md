# UdfPowMakeCompatible

- ea: `0x140013e10`
- end: `0x140013f7c`
- name: `UdfPowMakeCompatible`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400361d8`

## callees

- `0x14000ca10`
- `0x14000cad4`
- `0x140013e10`
- `0x140016fa8`
- `0x14003b730`
- `0x14004ce50`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140013f24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d9f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013f24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d9f8`

## pseudocode

```c
__int64 __fastcall UdfPowMakeCompatible(__int64 a1)
{
  __int64 v2; // rsi
  int v3; // ecx
  unsigned int v4; // ebx
  bool v5; // al

  v2 = *(_QWORD *)(a1 + 16);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 15, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids);
  }
  v3 = *(_DWORD *)(*(_QWORD *)(v2 + 104) + 4LL) & 0x10;
  v4 = 0;
  if ( (*(_DWORD *)(v2 + 48) & 0x20000000) != 0 )
  {
    if ( v3 )
      return 3221226048LL;
    v5 = 0;
  }
  else
  {
    v5 = v3 != 0;
  }
  if ( v5 )
    return 3221226048LL;
  UdfFlushVolume(a1, v2, 0, 1, 0, 0);
  UdfAcquireResource(a1, v2 + 2024, 0, 0);
  UdfMarkVolumeClean(a1);
  if ( (*(_DWORD *)(v2 + 2128) & 2) != 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 16, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids);
    }
    v4 = -1073741757;
  }
  else
  {
    UdfSeqCacheFlush(a1, v2);
  }
  ExReleaseResourceLite((PERESOURCE)(v2 + 2024));
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 17, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x140013e10  mov     [rsp+arg_8], rbx
0x140013e15  mov     [rsp+arg_10], rsi
0x140013e1a  push    r12
0x140013e1c  push    r14
0x140013e1e  push    r15
0x140013e20  sub     rsp, 40h
0x140013e24  mov     r14, rcx
0x140013e27  mov     rsi, [rcx+10h]
0x140013e2b  lea     r12, WPP_GLOBAL_Control
0x140013e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e39  cmp     rcx, r12
0x140013e3c  jz      short loc_140013E5C
0x140013e3e  test    dword ptr [rcx+2Ch], 20000000h
0x140013e45  jz      short loc_140013E5C
0x140013e47  mov     edx, 0Fh
0x140013e4c  lea     r8, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids
0x140013e53  mov     rcx, [rcx+18h]
0x140013e57  call    WPP_SF_
0x140013e5c  mov     rax, [rsi+68h]
0x140013e60  mov     ecx, [rax+4]
0x140013e63  and     ecx, 10h
0x140013e66  mov     eax, [rsi+30h]
0x140013e69  xor     ebx, ebx
0x140013e6b  bt      eax, 1Dh
0x140013e6f  jb      short loc_140013E78
0x140013e71  test    ecx, ecx
0x140013e73  setnz   al
0x140013e76  jmp     short loc_140013E82
0x140013e78  test    ecx, ecx
0x140013e7a  jnz     loc_140013F61
0x140013e80  mov     al, bl
0x140013e82  mov     [rsp+58h+arg_0], rsi
0x140013e87  mov     [rsp+58h+var_28], bl
0x140013e8b  test    al, al
0x140013e8d  jnz     loc_140013F61
0x140013e93  mov     [rsp+58h+var_30], bl; char
0x140013e97  mov     [rsp+58h+var_38], bl; char
0x140013e9b  mov     r9b, 1
0x140013e9e  xor     r8d, r8d
0x140013ea1  mov     rdx, rsi
0x140013ea4  mov     rcx, r14; int
0x140013ea7  call    UdfFlushVolume
0x140013eac  lea     r15, [rsi+7E8h]
0x140013eb3  xor     r9d, r9d
0x140013eb6  xor     r8d, r8d
0x140013eb9  mov     rdx, r15
0x140013ebc  mov     rcx, r14
0x140013ebf  call    UdfAcquireResource
0x140013ec4  mov     [rsp+58h+var_28], 1
0x140013ec9  xor     r9d, r9d
0x140013ecc  mov     r8b, 1
0x140013ecf  mov     rdx, rsi
0x140013ed2  mov     rcx, r14
0x140013ed5  call    UdfMarkVolumeClean
0x140013eda  mov     eax, [rsi+850h]
0x140013ee0  test    al, 2
0x140013ee2  jz      short loc_140013F15
0x140013ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140013eeb  cmp     rcx, r12
0x140013eee  jz      short loc_140013F0E
0x140013ef0  mov     eax, [rcx+2Ch]
0x140013ef3  bt      eax, 1Dh
0x140013ef7  jnb     short loc_140013F0E
0x140013ef9  mov     edx, 10h
0x140013efe  lea     r8, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids
0x140013f05  mov     rcx, [rcx+18h]
0x140013f09  call    WPP_SF_
0x140013f0e  mov     ebx, 0C0000043h
0x140013f13  jmp     short loc_140013F21
0x140013f15  mov     rdx, rsi
0x140013f18  mov     rcx, r14
0x140013f1b  call    UdfSeqCacheFlush
0x140013f20  nop
0x140013f21  mov     rcx, r15; Resource
0x140013f24  call    cs:__imp_ExReleaseResourceLite
0x140013f2b  nop     dword ptr [rax+rax+00h]
0x140013f30  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f37  cmp     rcx, r12
0x140013f3a  jz      short loc_140013F5D
0x140013f3c  test    dword ptr [rcx+2Ch], 20000000h
0x140013f43  jz      short loc_140013F5D
0x140013f45  mov     edx, 11h
0x140013f4a  mov     r9d, ebx
0x140013f4d  lea     r8, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids
0x140013f54  mov     rcx, [rcx+18h]
0x140013f58  call    WPP_SF_d
0x140013f5d  mov     eax, ebx
0x140013f5f  jmp     short loc_140013F66
0x140013f61  mov     eax, 0C0000240h
0x140013f66  mov     rbx, [rsp+58h+arg_8]
0x140013f6b  mov     rsi, [rsp+58h+arg_10]
0x140013f70  add     rsp, 40h
0x140013f74  pop     r15
0x140013f76  pop     r14
0x140013f78  pop     r12
0x140013f7a  retn
0x14001d9de  push    rbp
0x14001d9e0  sub     rsp, 30h
0x14001d9e4  mov     rbp, rdx
0x14001d9e7  cmp     byte ptr [rbp+30h], 0
0x14001d9eb  jz      short loc_14001DA05
0x14001d9ed  mov     rcx, [rbp+60h]
0x14001d9f1  add     rcx, 7E8h; Resource
0x14001d9f8  call    cs:__imp_ExReleaseResourceLite
0x14001d9ff  nop     dword ptr [rax+rax+00h]
0x14001da04  nop
0x14001da05  add     rsp, 30h
0x14001da09  pop     rbp
0x14001da0a  retn
```
