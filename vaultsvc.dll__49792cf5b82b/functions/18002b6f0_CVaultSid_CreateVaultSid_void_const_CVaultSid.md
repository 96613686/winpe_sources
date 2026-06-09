# CVaultSid::CreateVaultSid(void * const,CVaultSid * *)

- ea: `0x18002b6f0`
- end: `0x18002b87f`
- name: `?CreateVaultSid@CVaultSid@@SAKQEAXPEAPEAV1@@Z`
- size: `399`
- prototype: `unsigned int __fastcall(PSID pSourceSid, struct CVaultSid **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004110`
- `0x18002b3d0`
- `0x1800493d4`

## callees

- `0x180003140`
- `0x18002b6f0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002b805`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002b805`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7a7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b84d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b721`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b7b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b721`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b7b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultSid::CreateVaultSid(PSID pSourceSid, struct CVaultSid **a2)
{
  _DWORD *v4; // rdi
  DWORD LengthSid; // esi
  HLOCAL v7; // rax
  DWORD v8; // ebx
  DWORD LastError; // eax
  __int64 (__fastcall *v10)(_QWORD); // [rsp+20h] [rbp-48h] BYREF
  _DWORD *v11; // [rsp+28h] [rbp-40h]
  int v12; // [rsp+30h] [rbp-38h]

  v11 = 0;
  v12 = 0;
  v10 = AutoDereference<IVaultKeyManager>;
  v4 = LocalAlloc(0x40u, 0x18u);
  if ( v4 )
  {
    *(_QWORD *)v4 = &CVaultSid::`vftable';
    v4[2] = 1;
    *((_QWORD *)v4 + 2) = 0;
    v12 = 0;
    v11 = v4;
    if ( pSourceSid )
    {
      LengthSid = GetLengthSid(pSourceSid);
      v7 = LocalAlloc(0x40u, LengthSid);
      *((_QWORD *)v4 + 2) = v7;
      if ( !v7 )
      {
        v8 = 14;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 14);
LABEL_16:
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
        return v8;
      }
      if ( !CopySid(LengthSid, v7, pSourceSid) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, LastError);
        }
        v8 = GetLastError();
        if ( v8 )
          goto LABEL_16;
      }
    }
    *a2 = (struct CVaultSid *)v4;
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 14);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
  return 14;
}

```

## disassembly

```asm
0x18002b6f0  push    rbx
0x18002b6f2  push    rsi
0x18002b6f3  push    rdi
0x18002b6f4  push    r14
0x18002b6f6  sub     rsp, 48h
0x18002b6fa  mov     r14, rdx
0x18002b6fd  mov     rbx, rcx
0x18002b700  xor     esi, esi
0x18002b702  mov     [rsp+68h+var_40], rsi
0x18002b707  mov     [rsp+68h+var_38], esi
0x18002b70b  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18002b712  mov     [rsp+68h+var_48], rax
0x18002b717  mov     edx, 18h; uBytes
0x18002b71c  mov     ecx, 40h ; '@'; uFlags
0x18002b721  call    cs:__imp_LocalAlloc
0x18002b727  mov     rdi, rax
0x18002b72a  test    rax, rax
0x18002b72d  jnz     short loc_18002B77D
0x18002b72f  lea     rax, WPP_GLOBAL_Control
0x18002b736  mov     ebx, 0Eh
0x18002b73b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b742  cmp     rcx, rax
0x18002b745  jz      short loc_18002B766
0x18002b747  test    byte ptr [rcx+1Ch], 2
0x18002b74b  jz      short loc_18002B766
0x18002b74d  mov     edx, 2Ah ; '*'
0x18002b752  mov     r9d, ebx
0x18002b755  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18002b75c  mov     rcx, [rcx+10h]
0x18002b760  call    WPP_SF_d
0x18002b765  nop
0x18002b766  lea     rcx, [rsp+68h+var_48]
0x18002b76b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002b770  nop
0x18002b771  mov     eax, ebx
0x18002b773  add     rsp, 48h
0x18002b777  pop     r14
0x18002b779  pop     rdi
0x18002b77a  pop     rsi
0x18002b77b  pop     rbx
0x18002b77c  retn
0x18002b77d  lea     rax, ??_7CVaultSid@@6B@; const CVaultSid::`vftable'
0x18002b784  mov     [rdi], rax
0x18002b787  mov     dword ptr [rdi+8], 1
0x18002b78e  mov     [rdi+10h], rsi
0x18002b792  mov     [rsp+68h+var_38], esi
0x18002b796  mov     [rsp+68h+var_40], rdi
0x18002b79b  test    rbx, rbx
0x18002b79e  jz      loc_18002B870
0x18002b7a4  mov     rcx, rbx; pSid
0x18002b7a7  call    cs:__imp_GetLengthSid
0x18002b7ad  mov     esi, eax
0x18002b7af  mov     edx, eax; uBytes
0x18002b7b1  mov     ecx, 40h ; '@'; uFlags
0x18002b7b6  call    cs:__imp_LocalAlloc
0x18002b7bc  mov     [rdi+10h], rax
0x18002b7c0  test    rax, rax
0x18002b7c3  jnz     short loc_18002B7FD
0x18002b7c5  lea     rax, WPP_GLOBAL_Control
0x18002b7cc  mov     ebx, 0Eh
0x18002b7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7d8  cmp     rcx, rax
0x18002b7db  jz      short loc_18002B859
0x18002b7dd  test    byte ptr [rcx+1Ch], 2
0x18002b7e1  jz      short loc_18002B859
0x18002b7e3  mov     edx, 2Bh ; '+'
0x18002b7e8  mov     r9d, ebx
0x18002b7eb  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18002b7f2  mov     rcx, [rcx+10h]
0x18002b7f6  call    WPP_SF_d
0x18002b7fb  jmp     short loc_18002B859
0x18002b7fd  mov     r8, rbx; pSourceSid
0x18002b800  mov     rdx, rax; pDestinationSid
0x18002b803  mov     ecx, esi; nDestinationSidLength
0x18002b805  call    cs:__imp_CopySid
0x18002b80b  test    eax, eax
0x18002b80d  jnz     short loc_18002B870
0x18002b80f  lea     rax, WPP_GLOBAL_Control
0x18002b816  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b81d  cmp     rcx, rax
0x18002b820  jz      short loc_18002B84D
0x18002b822  test    byte ptr [rcx+1Ch], 2
0x18002b826  jz      short loc_18002B84D
0x18002b828  call    cs:__imp_GetLastError
0x18002b82e  mov     edx, 2Ch ; ','
0x18002b833  mov     r9d, eax
0x18002b836  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18002b83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b844  mov     rcx, [rcx+10h]
0x18002b848  call    WPP_SF_d
0x18002b84d  call    cs:__imp_GetLastError
0x18002b853  mov     ebx, eax
0x18002b855  test    eax, eax
0x18002b857  jz      short loc_18002B870
0x18002b859  lea     rcx, [rsp+68h+var_48]
0x18002b85e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002b863  nop
0x18002b864  mov     eax, ebx
0x18002b866  add     rsp, 48h
0x18002b86a  pop     r14
0x18002b86c  pop     rdi
0x18002b86d  pop     rsi
0x18002b86e  pop     rbx
0x18002b86f  retn
0x18002b870  mov     [r14], rdi
0x18002b873  xor     eax, eax
0x18002b875  add     rsp, 48h
0x18002b879  pop     r14
0x18002b87b  pop     rdi
0x18002b87c  pop     rsi
0x18002b87d  pop     rbx
0x18002b87e  retn
```
