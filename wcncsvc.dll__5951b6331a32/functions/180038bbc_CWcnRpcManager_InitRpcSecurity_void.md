# CWcnRpcManager::InitRpcSecurity(void)

- ea: `0x180038bbc`
- end: `0x180038d74`
- name: `?InitRpcSecurity@CWcnRpcManager@@AEAAJXZ`
- size: `440`
- prototype: `__int64 __fastcall(CWcnRpcManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038728`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180038bbc`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ce8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038c76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038cde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038c76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038cde`

## pseudocode

```c
__int64 __fastcall CWcnRpcManager::InitRpcSecurity(CWcnRpcManager *this)
{
  _BYTE *v1; // r10
  const char *Indent; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  const char *v5; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  signed int v8; // eax
  signed int LastError; // eax
  unsigned int v10; // eax
  __int64 v11; // r10
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp+8h] BYREF
  int v14; // [rsp+44h] [rbp+Ch]

  v14 = HIDWORD(this);
  SecurityDescriptorSize = 0;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 16, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, Indent);
    v1 = WPP_GLOBAL_Control;
  }
  if ( CWcnRpcManager::m_fSecurityInitialized )
  {
    v4 = 1;
    if ( v1 == (_BYTE *)&WPP_GLOBAL_Control )
      return v4;
    if ( v1[25] < 3u )
      goto LABEL_23;
    v5 = GetIndent(0);
    v7 = 17;
    goto LABEL_8;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:SYG:SYD:(A;;GA;;;SY)(A;;RC;;;S-1-5-80-3578261754-285310837-913589462-2834155770-667502746)(A;;RC;;;S-1-5-80-1"
          "428027539-3309602793-2678353003-1498846795-3763184142)S:(AU;FA;GA;;;WD)",
         1u,
         &CWcnRpcManager::m_pWcnRpcTransportSecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    SecurityDescriptorSize = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:SYG:SYD:(A;;GA;;;SY)(A;;RC;;;S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142)(A;;RC;;;BA)(A"
            ";;RC;;;IU)(A;;RC;;;LS)(A;;RC;;;NO)S:(AU;FA;GA;;;WD)",
           1u,
           &CWcnRpcManager::m_pWcnRpcClientSecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      v4 = 0;
      CWcnRpcManager::m_fSecurityInitialized = 1;
      goto LABEL_22;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = GetIndent(0);
        v7 = 19;
        goto LABEL_8;
      }
LABEL_23:
      if ( v1 != (_BYTE *)&WPP_GLOBAL_Control && ((v4 & 0x80000000) != 0 || v1[25] >= 6u) )
      {
        v10 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v11 + 16), 20, (unsigned int)WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, v10, v4);
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = GetIndent(0);
        v7 = 18;
LABEL_8:
        WPP_SF_s(*(_QWORD *)(v6 + 16), v7, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, v5);
LABEL_22:
        v1 = WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180038bbc  mov     rax, rsp
0x180038bbf  mov     [rax+10h], rbx
0x180038bc3  mov     [rax+18h], rbp
0x180038bc7  mov     [rax+8], rcx
0x180038bcb  push    r14
0x180038bcd  sub     rsp, 30h
0x180038bd1  mov     dword ptr [rax+8], 0
0x180038bd8  mov     r10, cs:WPP_GLOBAL_Control
0x180038bdf  lea     rbp, WPP_GLOBAL_Control
0x180038be6  lea     r14, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids
0x180038bed  cmp     r10, rbp
0x180038bf0  jz      short loc_180038C1E
0x180038bf2  cmp     byte ptr [r10+19h], 6
0x180038bf7  jb      short loc_180038C1E
0x180038bf9  mov     ecx, 1; int
0x180038bfe  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180038c03  mov     rcx, [r10+10h]
0x180038c07  mov     edx, 10h
0x180038c0c  mov     r9, rax
0x180038c0f  mov     r8, r14
0x180038c12  call    WPP_SF_s
0x180038c17  mov     r10, cs:WPP_GLOBAL_Control
0x180038c1e  cmp     cs:?m_fSecurityInitialized@CWcnRpcManager@@0_NA, 0; bool CWcnRpcManager::m_fSecurityInitialized
0x180038c25  jz      short loc_180038C5E
0x180038c27  mov     ebx, 1
0x180038c2c  cmp     r10, rbp
0x180038c2f  jz      loc_180038D61
0x180038c35  cmp     byte ptr [r10+19h], 3
0x180038c3a  jb      loc_180038D31
0x180038c40  xor     ecx, ecx; int
0x180038c42  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180038c47  lea     edx, [rbx+10h]
0x180038c4a  mov     rcx, [r10+10h]
0x180038c4e  mov     r9, rax
0x180038c51  mov     r8, r14
0x180038c54  call    WPP_SF_s
0x180038c59  jmp     loc_180038D2A
0x180038c5e  lea     r9, [rsp+38h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180038c63  mov     edx, 1; StringSDRevision
0x180038c68  lea     r8, ?m_pWcnRpcTransportSecurityDescriptor@CWcnRpcManager@@0PEAXEA; SecurityDescriptor
0x180038c6f  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;GA;;;SY)(A;;RC;;;S-1-5-80"...
0x180038c76  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180038c7c  test    eax, eax
0x180038c7e  jnz     short loc_180038CBE
0x180038c80  call    cs:__imp_GetLastError
0x180038c86  mov     ebx, eax
0x180038c88  test    eax, eax
0x180038c8a  jle     short loc_180038C95
0x180038c8c  movzx   ebx, ax
0x180038c8f  or      ebx, 80070000h
0x180038c95  mov     r10, cs:WPP_GLOBAL_Control
0x180038c9c  cmp     r10, rbp
0x180038c9f  jz      loc_180038D61
0x180038ca5  cmp     byte ptr [r10+19h], 2
0x180038caa  jb      loc_180038D31
0x180038cb0  xor     ecx, ecx; int
0x180038cb2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180038cb7  mov     edx, 12h
0x180038cbc  jmp     short loc_180038C4A
0x180038cbe  lea     r9, [rsp+38h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180038cc3  mov     [rsp+38h+SecurityDescriptorSize], 0
0x180038ccb  lea     r8, ?m_pWcnRpcClientSecurityDescriptor@CWcnRpcManager@@0PEAXEA; SecurityDescriptor
0x180038cd2  mov     edx, 1; StringSDRevision
0x180038cd7  lea     rcx, aOSygSydAGaSyAR; "O:SYG:SYD:(A;;GA;;;SY)(A;;RC;;;S-1-5-80"...
0x180038cde  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180038ce4  test    eax, eax
0x180038ce6  jnz     short loc_180038D21
0x180038ce8  call    cs:__imp_GetLastError
0x180038cee  mov     ebx, eax
0x180038cf0  test    eax, eax
0x180038cf2  jle     short loc_180038CFD
0x180038cf4  movzx   ebx, ax
0x180038cf7  or      ebx, 80070000h
0x180038cfd  mov     r10, cs:WPP_GLOBAL_Control
0x180038d04  cmp     r10, rbp
0x180038d07  jz      short loc_180038D61
0x180038d09  cmp     byte ptr [r10+19h], 2
0x180038d0e  jb      short loc_180038D31
0x180038d10  xor     ecx, ecx; int
0x180038d12  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180038d17  mov     edx, 13h
0x180038d1c  jmp     loc_180038C4A
0x180038d21  xor     ebx, ebx
0x180038d23  mov     cs:?m_fSecurityInitialized@CWcnRpcManager@@0_NA, 1; bool CWcnRpcManager::m_fSecurityInitialized
0x180038d2a  mov     r10, cs:WPP_GLOBAL_Control
0x180038d31  cmp     r10, rbp
0x180038d34  jz      short loc_180038D61
0x180038d36  test    ebx, ebx
0x180038d38  js      short loc_180038D41
0x180038d3a  cmp     byte ptr [r10+19h], 6
0x180038d3f  jb      short loc_180038D61
0x180038d41  or      ecx, 0FFFFFFFFh; int
0x180038d44  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180038d49  mov     rcx, [r10+10h]
0x180038d4d  mov     edx, 14h
0x180038d52  mov     r9, rax
0x180038d55  mov     [rsp+38h+var_18], ebx
0x180038d59  mov     r8, r14
0x180038d5c  call    WPP_SF_sd
0x180038d61  mov     rbp, [rsp+38h+arg_10]
0x180038d66  mov     eax, ebx
0x180038d68  mov     rbx, [rsp+38h+arg_8]
0x180038d6d  add     rsp, 30h
0x180038d71  pop     r14
0x180038d73  retn
```
