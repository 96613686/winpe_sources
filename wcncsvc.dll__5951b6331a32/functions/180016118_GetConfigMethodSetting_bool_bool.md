# GetConfigMethodSetting(bool &,bool &)

- ea: `0x180016118`
- end: `0x18001639a`
- name: `?GetConfigMethodSetting@@YAXAEA_N0@Z`
- size: `642`
- prototype: `void __fastcall(bool *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000b850`
- `0x180018204`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180005088`
- `0x180016118`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001634a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001634a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016197`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001626a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800162f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001626a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800162f0`

## string_xrefs

- `0x180016186`: `SYSTEM\CurrentControlSet\Services\wcncsvc\Parameters`
- `0x180016242`: `VirtualDisplayConfigMethodEnabled`
- `0x1800162c1`: `PhysicalPushButtonConfigMethodEnabled`

## pseudocode

```c
void __fastcall GetConfigMethodSetting(bool *a1, bool *a2)
{
  const char *Indent; // rax
  __int64 v5; // r10
  LSTATUS v6; // eax
  _BYTE *v7; // r10
  unsigned int v8; // eax
  __int64 v9; // r10
  char v10; // r11
  const char *v11; // rax
  __int64 v12; // r10
  unsigned int v13; // eax
  __int64 v14; // r10
  unsigned int v15; // eax
  __int64 v16; // r10
  unsigned int v17; // eax
  __int64 v18; // r10
  int pvData; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    Indent = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 189, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
  }
  *a1 = 1;
  hkey = 0;
  *a2 = 1;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\wcncsvc\\Parameters",
         0,
         0x20119u,
         &hkey);
  if ( !v6 )
    goto LABEL_13;
  if ( v6 == 2 || v6 == 1168 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_14;
    v11 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 190, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v11);
LABEL_13:
    v7 = WPP_GLOBAL_Control;
LABEL_14:
    if ( !hkey )
      goto LABEL_28;
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"VirtualDisplayConfigMethodEnabled", 0x10u, 0, &pvData, &pcbData) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v13 = (unsigned int)GetIndent(0);
        WPP_SF_sd(
          *(_QWORD *)(v14 + 16),
          192,
          (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids,
          v13,
          pvData);
      }
      *a1 = pvData != 0;
    }
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"PhysicalPushButtonConfigMethodEnabled", 0x10u, 0, &pvData, &pcbData) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v15 = (unsigned int)GetIndent(0);
        WPP_SF_sd(
          *(_QWORD *)(v16 + 16),
          193,
          (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids,
          v15,
          pvData);
      }
      *a2 = pvData != 0;
    }
    goto LABEL_25;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v9 + 16), 191, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v8, v10);
LABEL_25:
    v7 = WPP_GLOBAL_Control;
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    v7 = WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && v7[25] >= 4u )
  {
    v17 = (unsigned int)GetIndent(0);
    WPP_SF_sld(*(_QWORD *)(v18 + 16), 194, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v17, *a1, *a2);
  }
}

```

## disassembly

```asm
0x180016118  push    rbp
0x18001611a  push    rbx
0x18001611b  push    rdi
0x18001611c  push    r12
0x18001611e  push    r14
0x180016120  mov     rbp, rsp
0x180016123  sub     rsp, 40h
0x180016127  mov     rbx, rdx
0x18001612a  mov     rdi, rcx
0x18001612d  mov     r10, cs:WPP_GLOBAL_Control
0x180016134  lea     r14, WPP_GLOBAL_Control
0x18001613b  lea     r12, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016142  cmp     r10, r14
0x180016145  jz      short loc_180016169
0x180016147  cmp     byte ptr [r10+19h], 4
0x18001614c  jb      short loc_180016169
0x18001614e  xor     ecx, ecx; int
0x180016150  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016155  mov     rcx, [r10+10h]
0x180016159  mov     edx, 0BDh
0x18001615e  mov     r9, rax
0x180016161  mov     r8, r12
0x180016164  call    WPP_SF_s
0x180016169  lea     rax, [rbp+hkey]
0x18001616d  mov     byte ptr [rdi], 1
0x180016170  mov     r9d, 20119h; samDesired
0x180016176  mov     [rsp+40h+phkResult], rax; phkResult
0x18001617b  xor     r8d, r8d; ulOptions
0x18001617e  mov     [rbp+hkey], 0
0x180016186  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\wc"...
0x18001618d  mov     byte ptr [rbx], 1
0x180016190  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016197  call    cs:__imp_RegOpenKeyExW
0x18001619d  mov     r11d, eax
0x1800161a0  test    eax, eax
0x1800161a2  jz      short loc_18001621E
0x1800161a4  cmp     eax, 2
0x1800161a7  jz      short loc_1800161F0
0x1800161a9  cmp     eax, 490h
0x1800161ae  jz      short loc_1800161F0
0x1800161b0  mov     r10, cs:WPP_GLOBAL_Control
0x1800161b7  cmp     r10, r14
0x1800161ba  jz      loc_180016341
0x1800161c0  cmp     byte ptr [r10+19h], 2
0x1800161c5  jb      loc_180016341
0x1800161cb  xor     ecx, ecx; int
0x1800161cd  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800161d2  mov     rcx, [r10+10h]
0x1800161d6  mov     edx, 0BFh
0x1800161db  mov     r9, rax
0x1800161de  mov     dword ptr [rsp+40h+phkResult], r11d
0x1800161e3  mov     r8, r12
0x1800161e6  call    WPP_SF_sd
0x1800161eb  jmp     loc_18001633A
0x1800161f0  mov     r10, cs:WPP_GLOBAL_Control
0x1800161f7  cmp     r10, r14
0x1800161fa  jz      short loc_180016225
0x1800161fc  cmp     byte ptr [r10+19h], 2
0x180016201  jb      short loc_180016225
0x180016203  xor     ecx, ecx; int
0x180016205  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001620a  mov     rcx, [r10+10h]
0x18001620e  mov     edx, 0BEh
0x180016213  mov     r9, rax
0x180016216  mov     r8, r12
0x180016219  call    WPP_SF_s
0x18001621e  mov     r10, cs:WPP_GLOBAL_Control
0x180016225  mov     rcx, [rbp+hkey]; hkey
0x180016229  test    rcx, rcx
0x18001622c  jz      loc_180016357
0x180016232  lea     rax, [rbp+arg_8]
0x180016236  mov     [rbp+arg_0], 0
0x18001623d  mov     [rsp+40h+pcbData], rax; pcbData
0x180016242  lea     r8, aVirtualdisplay; "VirtualDisplayConfigMethodEnabled"
0x180016249  lea     rax, [rbp+arg_0]
0x18001624d  mov     [rbp+arg_8], 4
0x180016254  mov     [rsp+40h+pvData], rax; pvData
0x180016259  mov     r9d, 10h; dwFlags
0x18001625f  xor     edx, edx; lpSubKey
0x180016261  mov     [rsp+40h+phkResult], 0; pdwType
0x18001626a  call    cs:__imp_RegGetValueW
0x180016270  test    eax, eax
0x180016272  jnz     short loc_1800162B4
0x180016274  mov     r10, cs:WPP_GLOBAL_Control
0x18001627b  cmp     r10, r14
0x18001627e  jz      short loc_1800162AB
0x180016280  cmp     byte ptr [r10+19h], 4
0x180016285  jb      short loc_1800162AB
0x180016287  xor     ecx, ecx; int
0x180016289  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001628e  mov     r8d, [rbp+arg_0]
0x180016292  mov     edx, 0C0h
0x180016297  mov     rcx, [r10+10h]
0x18001629b  mov     r9, rax
0x18001629e  mov     dword ptr [rsp+40h+phkResult], r8d
0x1800162a3  mov     r8, r12
0x1800162a6  call    WPP_SF_sd
0x1800162ab  cmp     [rbp+arg_0], 0
0x1800162af  setnbe  al
0x1800162b2  mov     [rdi], al
0x1800162b4  mov     rcx, [rbp+hkey]; hkey
0x1800162b8  lea     rax, [rbp+arg_8]
0x1800162bc  mov     [rsp+40h+pcbData], rax; pcbData
0x1800162c1  lea     r8, aPhysicalpushbu; "PhysicalPushButtonConfigMethodEnabled"
0x1800162c8  lea     rax, [rbp+arg_0]
0x1800162cc  mov     [rbp+arg_0], 0
0x1800162d3  mov     [rsp+40h+pvData], rax; pvData
0x1800162d8  mov     r9d, 10h; dwFlags
0x1800162de  xor     edx, edx; lpSubKey
0x1800162e0  mov     [rsp+40h+phkResult], 0; pdwType
0x1800162e9  mov     [rbp+arg_8], 4
0x1800162f0  call    cs:__imp_RegGetValueW
0x1800162f6  test    eax, eax
0x1800162f8  jnz     short loc_18001633A
0x1800162fa  mov     r10, cs:WPP_GLOBAL_Control
0x180016301  cmp     r10, r14
0x180016304  jz      short loc_180016331
0x180016306  cmp     byte ptr [r10+19h], 4
0x18001630b  jb      short loc_180016331
0x18001630d  xor     ecx, ecx; int
0x18001630f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016314  mov     r8d, [rbp+arg_0]
0x180016318  mov     edx, 0C1h
0x18001631d  mov     rcx, [r10+10h]
0x180016321  mov     r9, rax
0x180016324  mov     dword ptr [rsp+40h+phkResult], r8d
0x180016329  mov     r8, r12
0x18001632c  call    WPP_SF_sd
0x180016331  cmp     [rbp+arg_0], 0
0x180016335  setnbe  al
0x180016338  mov     [rbx], al
0x18001633a  mov     r10, cs:WPP_GLOBAL_Control
0x180016341  mov     rcx, [rbp+hkey]; hKey
0x180016345  test    rcx, rcx
0x180016348  jz      short loc_180016357
0x18001634a  call    cs:__imp_RegCloseKey
0x180016350  mov     r10, cs:WPP_GLOBAL_Control
0x180016357  cmp     r10, r14
0x18001635a  jz      short loc_18001638E
0x18001635c  cmp     byte ptr [r10+19h], 4
0x180016361  jb      short loc_18001638E
0x180016363  xor     ecx, ecx; int
0x180016365  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001636a  movzx   ecx, byte ptr [rbx]
0x18001636d  mov     edx, 0C2h
0x180016372  movzx   r9d, byte ptr [rdi]
0x180016376  mov     r8, r12
0x180016379  mov     dword ptr [rsp+40h+pvData], ecx
0x18001637d  mov     rcx, [r10+10h]
0x180016381  mov     dword ptr [rsp+40h+phkResult], r9d
0x180016386  mov     r9, rax
0x180016389  call    WPP_SF_sld
0x18001638e  add     rsp, 40h
0x180016392  pop     r14
0x180016394  pop     r12
0x180016396  pop     rdi
0x180016397  pop     rbx
0x180016398  pop     rbp
0x180016399  retn
```
