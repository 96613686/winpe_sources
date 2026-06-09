# SsUpdateServerNameList

- ea: `0x18002f8b8`
- end: `0x18002fc46`
- name: `SsUpdateServerNameList`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c750`

## callees

- `0x180008ca0`
- `0x18000b9a0`
- `0x18001deb0`
- `0x18001e80c`
- `0x180020de8`
- `0x18002f444`
- `0x18002f82c`
- `0x18002f8b8`
- `0x18002fc4c`
- `0x18003b728`
- `0x18003bab4`
- `0x1800435ec`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fa87`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fbdd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fa87`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fbdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f8ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fa4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fba4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f8ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fa4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f97a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f97a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc1a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f9d3`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f9d3`
- `ntdll!RtlReleaseResource` at `0x18002fc0c`
- `ntdll!RtlReleaseResource` at `0x18002fc0c`

## pseudocode

```c
__int64 SsUpdateServerNameList()
{
  _DWORD *v0; // rax
  _DWORD *v1; // rbx
  unsigned int InfoCommon; // eax
  unsigned int v4; // edi
  unsigned int v5; // esi
  unsigned int v6; // r13d
  _QWORD *v7; // rdi
  _WORD *v8; // rbx
  size_t v9; // r14
  int v10; // r15d
  const void *v11; // r12
  _QWORD *v12; // rax
  _DWORD *v13; // rax
  int v14; // r15d
  _QWORD *v15; // rcx
  _QWORD *v16; // rdx
  __int64 v17; // rax
  SIZE_T v18; // r14
  _QWORD *v19; // rax
  _QWORD *v20; // rbx
  __int64 v21; // rax
  SIZE_T uBytes; // [rsp+20h] [rbp-298h]
  _WORD *hMem; // [rsp+30h] [rbp-288h]
  int v24; // [rsp+3Ch] [rbp-27Ch] BYREF
  unsigned int v25; // [rsp+40h] [rbp-278h]
  WCHAR SourceString[264]; // [rsp+50h] [rbp-268h] BYREF

  v0 = LocalAlloc(0x40u, 0x60u);
  v1 = v0;
  if ( !v0 )
    return 8;
  v0[16] = 2;
  v0[23] = 0;
  LODWORD(uBytes) = -1;
  InfoCommon = SsServerFsControlGetInfoCommonEx(qword_18005CDB8, 0x14601Fu, v0, uBytes);
  v4 = v1[20];
  v5 = InfoCommon;
  v25 = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, v4, v1[21]);
  }
  LocalFree(v1);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, v5);
    }
  }
  else
  {
    RtlAcquireResourceExclusive(&Resource, 1u);
    v6 = 0;
    while ( v6 < v4 )
    {
      v7 = ::hMem;
      v8 = *(_WORD **)(56LL * v6 + 8);
      v9 = *(unsigned int *)(56LL * v6 + 0x18);
      v10 = *(_DWORD *)(56LL * v6 + 0x30);
      v11 = *(const void **)(56LL * v6 + 0x10);
      hMem = v8;
      if ( !::hMem )
        goto LABEL_19;
      do
      {
        if ( *((_DWORD *)v7 + 67) == (_DWORD)v9 && !memcmp_0(v7 + 1, v11, v9) )
          break;
        v7 = (_QWORD *)*v7;
      }
      while ( v7 );
      if ( !v7 )
      {
LABEL_19:
        v12 = LocalAlloc(0x40u, 0x540u);
        v7 = v12;
        if ( !v12 )
          goto LABEL_39;
        memset_0(v12, 0, 0x540u);
        v7[34] = v7 + 103;
        _o_wcscpy_s(v7 + 103, 260);
        memcpy_0(v7 + 1, v11, v9);
        v13 = (_DWORD *)v7 + 71;
        *((_BYTE *)v7 + v9 + 8) = 0;
        *((_DWORD *)v7 + 67) = v9;
        if ( !::hMem )
          *v13 |= 1u;
        if ( (v10 & 4) != 0 )
          *v13 |= 2u;
        v14 = v10 & 8;
        *((_DWORD *)v7 + 72) = v14 != 0;
        v24 = 522;
        if ( !(unsigned int)SsGetNetBIOSName(v7 + 38, SourceString) )
          ConfigureMachineAlias(SourceString);
        if ( !(unsigned int)SsGetFQDN((const wchar_t *)v7 + 152, SourceString, &v24, v14 != 0) )
          ConfigureMachineAlias(SourceString);
        SsUpdateMachineAliases(qword_18005CDB8);
        *v7 = 0;
        SsSetExportedServerType(v7, 0, 0);
        v15 = ::hMem;
        if ( ::hMem )
        {
          v16 = *(_QWORD **)::hMem;
          if ( *(_QWORD *)::hMem )
          {
            do
            {
              v15 = v16;
              v16 = (_QWORD *)*v16;
            }
            while ( v16 );
          }
          *v15 = v7;
        }
        else
        {
          ::hMem = v7;
        }
      }
      v17 = -1;
      do
        ++v17;
      while ( v8[v17] );
      v18 = (unsigned int)(2 * v17 + 26);
      v19 = LocalAlloc(0x40u, v18);
      v20 = v19;
      if ( !v19 )
      {
LABEL_39:
        v5 = 8;
        break;
      }
      memset_0(v19, 0, (unsigned int)v18);
      v20[1] = v20 + 3;
      v21 = -1;
      do
        ++v21;
      while ( hMem[v21] );
      _o_wcscpy_s(v20 + 3, (unsigned int)(v21 + 1));
      ++v6;
      *v20 = v7[37];
      v7[37] = v20;
      v4 = v25;
    }
  }
  RtlReleaseResource(&Resource);
  return v5;
}

```

## disassembly

```asm
0x18002f8b8  push    rbx
0x18002f8ba  push    rbp
0x18002f8bb  push    rsi
0x18002f8bc  push    rdi
0x18002f8bd  push    r12
0x18002f8bf  push    r13
0x18002f8c1  push    r14
0x18002f8c3  push    r15
0x18002f8c5  sub     rsp, 278h
0x18002f8cc  mov     rax, cs:__security_cookie
0x18002f8d3  xor     rax, rsp
0x18002f8d6  mov     [rsp+2B8h+var_58], rax
0x18002f8de  xor     r12d, r12d
0x18002f8e1  mov     [rsp+2B8h+hMem], r12
0x18002f8e6  lea     edx, [r12+60h]; uBytes
0x18002f8eb  lea     ecx, [rdx-20h]; uFlags
0x18002f8ee  call    cs:__imp_LocalAlloc
0x18002f8f4  mov     rbx, rax
0x18002f8f7  test    rax, rax
0x18002f8fa  jnz     short loc_18002F904
0x18002f8fc  lea     eax, [rbx+8]
0x18002f8ff  jmp     loc_18002FC22
0x18002f904  mov     dword ptr [rax+40h], 2
0x18002f90b  lea     r9, [rsp+2B8h+hMem]
0x18002f910  mov     [rax+5Ch], r12d
0x18002f914  mov     r8, rbx; hMem
0x18002f917  mov     rcx, cs:qword_18005CDB8; FileHandle
0x18002f91e  mov     edx, 14601Fh; FsControlCode
0x18002f923  mov     dword ptr [rsp+2B8h+uBytes], 0FFFFFFFFh; uBytes
0x18002f92b  call    SsServerFsControlGetInfoCommonEx
0x18002f930  mov     edi, [rbx+50h]
0x18002f933  mov     esi, eax
0x18002f935  mov     [rsp+2B8h+var_278], edi
0x18002f939  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f940  lea     r14, WPP_GLOBAL_Control
0x18002f947  cmp     rcx, r14
0x18002f94a  jz      short loc_18002F977
0x18002f94c  test    byte ptr [rcx+1Ch], 1
0x18002f950  jz      short loc_18002F977
0x18002f952  cmp     byte ptr [rcx+19h], 2
0x18002f956  jb      short loc_18002F977
0x18002f958  mov     eax, [rbx+54h]
0x18002f95b  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f962  mov     rcx, [rcx+10h]
0x18002f966  mov     edx, 11h
0x18002f96b  mov     r9d, edi
0x18002f96e  mov     dword ptr [rsp+2B8h+uBytes], eax
0x18002f972  call    WPP_SF_Dd
0x18002f977  mov     rcx, rbx; hMem
0x18002f97a  call    cs:__imp_LocalFree
0x18002f980  mov     rbp, [rsp+2B8h+hMem]
0x18002f985  test    esi, esi
0x18002f987  jz      short loc_18002F9CA
0x18002f989  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f990  cmp     rcx, r14
0x18002f993  jz      loc_18002FC05
0x18002f999  test    byte ptr [rcx+1Ch], 1
0x18002f99d  jz      loc_18002FC05
0x18002f9a3  cmp     byte ptr [rcx+19h], 1
0x18002f9a7  jb      loc_18002FC05
0x18002f9ad  mov     rcx, [rcx+10h]
0x18002f9b1  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f9b8  mov     edx, 12h
0x18002f9bd  mov     r9d, esi
0x18002f9c0  call    WPP_SF_d
0x18002f9c5  jmp     loc_18002FC05
0x18002f9ca  mov     dl, 1; Wait
0x18002f9cc  lea     rcx, Resource; Resource
0x18002f9d3  call    cs:__imp_RtlAcquireResourceExclusive
0x18002f9d9  mov     r13d, r12d
0x18002f9dc  cmp     r13d, edi
0x18002f9df  jnb     loc_18002FC05
0x18002f9e5  mov     rdi, cs:hMem
0x18002f9ec  mov     eax, r13d
0x18002f9ef  imul    rcx, rax, 38h ; '8'
0x18002f9f3  mov     rbx, [rcx+rbp+8]
0x18002f9f8  mov     r14d, [rcx+rbp+18h]
0x18002f9fd  mov     r15d, [rcx+rbp+30h]
0x18002fa02  mov     r12, [rcx+rbp+10h]
0x18002fa07  mov     [rsp+2B8h+hMem], rbx
0x18002fa0c  test    rdi, rdi
0x18002fa0f  jz      short loc_18002FA42
0x18002fa11  cmp     [rdi+10Ch], r14d
0x18002fa18  jnz     short loc_18002FA2D
0x18002fa1a  mov     r8, r14; Size
0x18002fa1d  lea     rcx, [rdi+8]; Buf1
0x18002fa21  mov     rdx, r12; Buf2
0x18002fa24  call    memcmp_0
0x18002fa29  test    eax, eax
0x18002fa2b  jz      short loc_18002FA35
0x18002fa2d  mov     rdi, [rdi]
0x18002fa30  test    rdi, rdi
0x18002fa33  jnz     short loc_18002FA11
0x18002fa35  test    rdi, rdi
0x18002fa38  jz      short loc_18002FA42
0x18002fa3a  xor     r12d, r12d
0x18002fa3d  jmp     loc_18002FB85
0x18002fa42  mov     ebx, 540h
0x18002fa47  mov     ecx, 40h ; '@'; uFlags
0x18002fa4c  mov     edx, ebx; uBytes
0x18002fa4e  call    cs:__imp_LocalAlloc
0x18002fa54  mov     rdi, rax
0x18002fa57  test    rax, rax
0x18002fa5a  jz      loc_18002FC00
0x18002fa60  mov     r8d, ebx; Size
0x18002fa63  xor     edx, edx; Val
0x18002fa65  mov     rcx, rax; void *
0x18002fa68  call    memset_0
0x18002fa6d  lea     rcx, [rdi+338h]
0x18002fa74  mov     edx, 104h
0x18002fa79  lea     r8, pszDest
0x18002fa80  mov     [rdi+110h], rcx
0x18002fa87  call    cs:__imp__o_wcscpy_s
0x18002fa8d  lea     rcx, [rdi+8]; void *
0x18002fa91  mov     r8, r14; Size
0x18002fa94  mov     rdx, r12; Src
0x18002fa97  call    memcpy_0
0x18002fa9c  xor     r12d, r12d
0x18002fa9f  lea     rax, [rdi+11Ch]
0x18002faa6  mov     [r14+rdi+8], r12b
0x18002faab  mov     [rdi+10Ch], r14d
0x18002fab2  cmp     cs:hMem, r12
0x18002fab9  jnz     short loc_18002FABE
0x18002fabb  or      dword ptr [rax], 1
0x18002fabe  test    r15b, 4
0x18002fac2  jz      short loc_18002FAC7
0x18002fac4  or      dword ptr [rax], 2
0x18002fac7  mov     eax, r12d
0x18002faca  lea     rbx, [rdi+130h]
0x18002fad1  and     r15d, 8
0x18002fad5  lea     r8, [rsp+2B8h+var_280]
0x18002fada  lea     rdx, [rsp+2B8h+SourceString]; void *
0x18002fadf  mov     rcx, rbx; Src
0x18002fae2  setnz   al
0x18002fae5  mov     [rdi+120h], eax
0x18002faeb  mov     eax, 20Ah
0x18002faf0  mov     [rsp+2B8h+var_27C], eax
0x18002faf4  mov     [rsp+2B8h+var_280], eax
0x18002faf8  call    SsGetNetBIOSName
0x18002fafd  test    eax, eax
0x18002faff  jnz     short loc_18002FB0D
0x18002fb01  mov     dl, 1
0x18002fb03  lea     rcx, [rsp+2B8h+SourceString]; SourceString
0x18002fb08  call    ConfigureMachineAlias
0x18002fb0d  test    r15d, r15d
0x18002fb10  lea     r8, [rsp+2B8h+var_27C]
0x18002fb15  lea     rdx, [rsp+2B8h+SourceString]; void *
0x18002fb1a  mov     rcx, rbx; Src
0x18002fb1d  setnz   r9b
0x18002fb21  call    SsGetFQDN
0x18002fb26  test    eax, eax
0x18002fb28  jnz     short loc_18002FB36
0x18002fb2a  mov     dl, 1
0x18002fb2c  lea     rcx, [rsp+2B8h+SourceString]; SourceString
0x18002fb31  call    ConfigureMachineAlias
0x18002fb36  mov     rcx, cs:qword_18005CDB8; FileHandle
0x18002fb3d  call    SsUpdateMachineAliases
0x18002fb42  xor     r8d, r8d
0x18002fb45  mov     [rdi], r12
0x18002fb48  xor     edx, edx
0x18002fb4a  mov     rcx, rdi
0x18002fb4d  call    SsSetExportedServerType
0x18002fb52  mov     rcx, cs:hMem
0x18002fb59  test    rcx, rcx
0x18002fb5c  jnz     short loc_18002FB67
0x18002fb5e  mov     cs:hMem, rdi
0x18002fb65  jmp     short loc_18002FB80
0x18002fb67  mov     rdx, [rcx]
0x18002fb6a  test    rdx, rdx
0x18002fb6d  jz      short loc_18002FB7D
0x18002fb6f  mov     rax, [rdx]
0x18002fb72  mov     rcx, rdx
0x18002fb75  mov     rdx, rax
0x18002fb78  test    rax, rax
0x18002fb7b  jnz     short loc_18002FB6F
0x18002fb7d  mov     [rcx], rdi
0x18002fb80  mov     rbx, [rsp+2B8h+hMem]
0x18002fb85  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fb89  inc     rax
0x18002fb8c  cmp     [rbx+rax*2], r12w
0x18002fb91  jnz     short loc_18002FB89
0x18002fb93  lea     eax, ds:1Ah[rax*2]
0x18002fb9a  mov     ecx, 40h ; '@'; uFlags
0x18002fb9f  mov     edx, eax; uBytes
0x18002fba1  mov     r14d, eax
0x18002fba4  call    cs:__imp_LocalAlloc
0x18002fbaa  mov     rbx, rax
0x18002fbad  test    rax, rax
0x18002fbb0  jz      short loc_18002FC00
0x18002fbb2  mov     r8d, r14d; Size
0x18002fbb5  xor     edx, edx; Val
0x18002fbb7  mov     rcx, rax; void *
0x18002fbba  call    memset_0
0x18002fbbf  mov     r8, [rsp+2B8h+hMem]
0x18002fbc4  lea     rcx, [rbx+18h]
0x18002fbc8  mov     [rbx+8], rcx
0x18002fbcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fbd0  inc     rax
0x18002fbd3  cmp     [r8+rax*2], r12w
0x18002fbd8  jnz     short loc_18002FBD0
0x18002fbda  lea     edx, [rax+1]
0x18002fbdd  call    cs:__imp__o_wcscpy_s
0x18002fbe3  mov     rax, [rdi+128h]
0x18002fbea  inc     r13d
0x18002fbed  mov     [rbx], rax
0x18002fbf0  mov     [rdi+128h], rbx
0x18002fbf7  mov     edi, [rsp+2B8h+var_278]
0x18002fbfb  jmp     loc_18002F9DC
0x18002fc00  mov     esi, 8
0x18002fc05  lea     rcx, Resource; Resource
0x18002fc0c  call    cs:__imp_RtlReleaseResource
0x18002fc12  test    rbp, rbp
0x18002fc15  jz      short loc_18002FC20
0x18002fc17  mov     rcx, rbp; hMem
0x18002fc1a  call    cs:__imp_LocalFree
0x18002fc20  mov     eax, esi
0x18002fc22  mov     rcx, [rsp+2B8h+var_58]
0x18002fc2a  xor     rcx, rsp; StackCookie
0x18002fc2d  call    __security_check_cookie
0x18002fc32  add     rsp, 278h
0x18002fc39  pop     r15
0x18002fc3b  pop     r14
0x18002fc3d  pop     r13
0x18002fc3f  pop     r12
0x18002fc41  pop     rdi
0x18002fc42  pop     rsi
0x18002fc43  pop     rbp
0x18002fc44  pop     rbx
0x18002fc45  retn
```
