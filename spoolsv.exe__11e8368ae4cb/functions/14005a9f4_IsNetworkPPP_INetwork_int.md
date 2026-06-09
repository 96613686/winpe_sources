# IsNetworkPPP(INetwork *,int *)

- ea: `0x14005a9f4`
- end: `0x14005ac75`
- name: `?IsNetworkPPP@@YAJPEAUINetwork@@PEAH@Z`
- size: `641`
- prototype: `__int64 __fastcall(struct INetwork *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14005a6f8`

## callees

- `0x1400041c0`
- `0x14002abc0`
- `0x14005a9f4`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x14005ab91`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x14005ab91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005aad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005ac43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005aad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005ac43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ab68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ab68`
- `KERNEL32!WideCharToMultiByte` at `0x14005ab5e`
- `KERNEL32!WideCharToMultiByte` at `0x14005ab5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005abd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005abd6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14005ab27`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14005ab27`
- `IPHLPAPI!GetAdaptersAddresses` at `0x14005aaab`
- `IPHLPAPI!GetAdaptersAddresses` at `0x14005aaab`

## pseudocode

```c
__int64 __fastcall IsNetworkPPP(struct INetwork *a1, int *a2)
{
  IP_ADAPTER_ADDRESSES_LH *v3; // rsi
  int v4; // r14d
  struct INetworkVtbl *lpVtbl; // rax
  int v6; // ebx
  signed int AdaptersAddresses; // eax
  __int64 v8; // rcx
  signed int LastError; // eax
  IP_ADAPTER_ADDRESSES_LH *i; // rdi
  bool v11; // zf
  int v12; // eax
  __int64 v14; // [rsp+40h] [rbp-29h] BYREF
  ULONG SizePointer; // [rsp+48h] [rbp-21h] BYREF
  __int64 v16; // [rsp+50h] [rbp-19h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-11h] BYREF
  IID rclsid; // [rsp+60h] [rbp-9h] BYREF
  CHAR MultiByteStr[40]; // [rsp+70h] [rbp+7h] BYREF

  v16 = 0;
  v3 = 0;
  v14 = 0;
  *a2 = 0;
  v4 = 0;
  lpVtbl = a1->lpVtbl;
  SizePointer = 10000;
  v6 = ((__int64 (__fastcall *)(struct INetwork *, __int64 *))lpVtbl->GetNetworkConnections)(a1, &v16);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, 1, &v14, 0);
  if ( !v6 && v14 )
  {
    while ( 1 )
    {
      v3 = (IP_ADAPTER_ADDRESSES_LH *)DllAllocSplMem(SizePointer);
      if ( !v3 )
      {
        v6 = -2147024882;
        goto LABEL_32;
      }
      AdaptersAddresses = GetAdaptersAddresses(0, 0x2Fu, 0, v3, &SizePointer);
      v6 = AdaptersAddresses;
      if ( AdaptersAddresses > 0 )
        v6 = (unsigned __int16)AdaptersAddresses | 0x80070000;
      if ( v6 != -2147024785 )
        break;
      HeapFree(g_hSpoolssHeap, 0, v3);
    }
    if ( !v6 )
    {
      v8 = v14;
      do
      {
        if ( !v8 || v4 )
          break;
        lpsz = 0;
        rclsid = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v8 + 96LL))(v8, &rclsid);
        if ( v6 >= 0 )
          v6 = StringFromCLSID(&rclsid, &lpsz);
        if ( !WideCharToMultiByte(0, 0, lpsz, -1, MultiByteStr, 40, 0, 0) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
        if ( v6 >= 0 )
        {
          for ( i = v3; i; i = i->Next )
          {
            if ( !(unsigned int)_o__stricmp(i->AdapterName, MultiByteStr) && i->IfType == 23 )
            {
              v4 = 1;
              break;
            }
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v8 = 0;
        v14 = 0;
        if ( lpsz )
        {
          CoTaskMemFree(lpsz);
          v8 = v14;
          lpsz = 0;
        }
        v11 = v6 == 0;
        if ( v6 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, 1, &v14);
          v8 = v14;
          v6 = v12;
          v11 = v12 == 0;
        }
      }
      while ( v11 );
    }
  }
LABEL_32:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v3 )
    HeapFree(g_hSpoolssHeap, 0, v3);
  if ( v6 >= 0 )
    *a2 = v4;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14005a9f4  mov     [rsp-8+arg_10], rbx
0x14005a9f9  push    rbp
0x14005a9fa  push    rsi
0x14005a9fb  push    rdi
0x14005a9fc  push    r14
0x14005a9fe  push    r15
0x14005aa00  lea     rbp, [rsp-37h]
0x14005aa05  sub     rsp, 0A0h
0x14005aa0c  mov     rax, cs:__security_cookie
0x14005aa13  xor     rax, rsp
0x14005aa16  mov     [rbp+57h+var_28], rax
0x14005aa1a  mov     r15, rdx
0x14005aa1d  mov     [rbp+57h+var_70], 0
0x14005aa25  xor     esi, esi
0x14005aa27  mov     [rbp+57h+var_80], 0
0x14005aa2f  mov     [rdx], esi
0x14005aa31  xor     r14d, r14d
0x14005aa34  mov     rax, [rcx]
0x14005aa37  lea     rdx, [rbp+57h+var_70]
0x14005aa3b  mov     [rbp+57h+var_78], 2710h
0x14005aa42  mov     rax, [rax+68h]
0x14005aa46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aa4b  mov     ebx, eax
0x14005aa4d  test    eax, eax
0x14005aa4f  js      short loc_14005AA6D
0x14005aa51  mov     rcx, [rbp+57h+var_70]
0x14005aa55  lea     r8, [rbp+57h+var_80]
0x14005aa59  xor     r9d, r9d
0x14005aa5c  lea     edx, [rsi+1]
0x14005aa5f  mov     rax, [rcx]
0x14005aa62  mov     rax, [rax+40h]
0x14005aa66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aa6b  mov     ebx, eax
0x14005aa6d  test    ebx, ebx
0x14005aa6f  jnz     loc_14005AC15
0x14005aa75  mov     rcx, [rbp+57h+var_80]
0x14005aa79  test    rcx, rcx
0x14005aa7c  jz      loc_14005AC15
0x14005aa82  mov     ecx, [rbp+57h+var_78]; dwBytes
0x14005aa85  call    DllAllocSplMem
0x14005aa8a  mov     rsi, rax
0x14005aa8d  test    rax, rax
0x14005aa90  jz      loc_14005ABA7
0x14005aa96  xor     r8d, r8d; Reserved
0x14005aa99  lea     rax, [rbp+57h+var_78]
0x14005aa9d  mov     r9, rsi; AdapterAddresses
0x14005aaa0  mov     [rsp+0C0h+SizePointer], rax; SizePointer
0x14005aaa5  xor     ecx, ecx; Family
0x14005aaa7  lea     edx, [r8+2Fh]; Flags
0x14005aaab  call    cs:__imp_GetAdaptersAddresses
0x14005aab1  mov     ebx, eax
0x14005aab3  test    eax, eax
0x14005aab5  jle     short loc_14005AAC0
0x14005aab7  movzx   ebx, ax
0x14005aaba  or      ebx, 80070000h
0x14005aac0  cmp     ebx, 8007006Fh
0x14005aac6  jnz     short loc_14005AADC
0x14005aac8  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005aacf  mov     r8, rsi; lpMem
0x14005aad2  xor     edx, edx; dwFlags
0x14005aad4  call    cs:__imp_HeapFree
0x14005aada  jmp     short loc_14005AA82
0x14005aadc  test    ebx, ebx
0x14005aade  jnz     loc_14005AC15
0x14005aae4  mov     rcx, [rbp+57h+var_80]
0x14005aae8  test    rcx, rcx
0x14005aaeb  jz      loc_14005AC15
0x14005aaf1  test    r14d, r14d
0x14005aaf4  jnz     loc_14005AC15
0x14005aafa  xorps   xmm0, xmm0
0x14005aafd  mov     [rbp+57h+lpsz], 0
0x14005ab05  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x14005ab09  mov     rax, [rcx]
0x14005ab0c  lea     rdx, [rbp+57h+rclsid]
0x14005ab10  mov     rax, [rax+60h]
0x14005ab14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ab19  mov     ebx, eax
0x14005ab1b  test    eax, eax
0x14005ab1d  js      short loc_14005AB2F
0x14005ab1f  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x14005ab23  lea     rcx, [rbp+57h+rclsid]; rclsid
0x14005ab27  call    cs:__imp_StringFromCLSID
0x14005ab2d  mov     ebx, eax
0x14005ab2f  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x14005ab33  lea     rax, [rbp+57h+MultiByteStr]
0x14005ab37  mov     [rsp+0C0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14005ab40  or      r9d, 0FFFFFFFFh; cchWideChar
0x14005ab44  mov     [rsp+0C0h+lpDefaultChar], 0; lpDefaultChar
0x14005ab4d  xor     edx, edx; dwFlags
0x14005ab4f  mov     [rsp+0C0h+cbMultiByte], 28h ; '('; cbMultiByte
0x14005ab57  xor     ecx, ecx; CodePage
0x14005ab59  mov     [rsp+0C0h+SizePointer], rax; lpMultiByteStr
0x14005ab5e  call    cs:__imp_WideCharToMultiByte
0x14005ab64  test    eax, eax
0x14005ab66  jnz     short loc_14005AB7D
0x14005ab68  call    cs:__imp_GetLastError
0x14005ab6e  mov     ebx, eax
0x14005ab70  test    eax, eax
0x14005ab72  jle     short loc_14005AB7D
0x14005ab74  movzx   ebx, ax
0x14005ab77  or      ebx, 80070000h
0x14005ab7d  test    ebx, ebx
0x14005ab7f  js      short loc_14005ABB4
0x14005ab81  mov     rdi, rsi
0x14005ab84  test    rdi, rdi
0x14005ab87  jz      short loc_14005ABB4
0x14005ab89  mov     rcx, [rdi+10h]
0x14005ab8d  lea     rdx, [rbp+57h+MultiByteStr]
0x14005ab91  call    cs:__imp__o__stricmp
0x14005ab97  test    eax, eax
0x14005ab99  jnz     short loc_14005ABA1
0x14005ab9b  cmp     dword ptr [rdi+64h], 17h
0x14005ab9f  jz      short loc_14005ABAE
0x14005aba1  mov     rdi, [rdi+8]
0x14005aba5  jmp     short loc_14005AB84
0x14005aba7  mov     ebx, 8007000Eh
0x14005abac  jmp     short loc_14005AC15
0x14005abae  mov     r14d, 1
0x14005abb4  mov     rcx, [rbp+57h+var_80]
0x14005abb8  mov     rax, [rcx]
0x14005abbb  mov     rax, [rax+10h]
0x14005abbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005abc4  mov     rax, [rbp+57h+lpsz]
0x14005abc8  xor     ecx, ecx
0x14005abca  mov     [rbp+57h+var_80], rcx
0x14005abce  test    rax, rax
0x14005abd1  jz      short loc_14005ABE8
0x14005abd3  mov     rcx, rax; pv
0x14005abd6  call    cs:__imp_CoTaskMemFree
0x14005abdc  mov     rcx, [rbp+57h+var_80]
0x14005abe0  mov     [rbp+57h+lpsz], 0
0x14005abe8  test    ebx, ebx
0x14005abea  js      short loc_14005AC0F
0x14005abec  mov     rcx, [rbp+57h+var_70]
0x14005abf0  lea     r8, [rbp+57h+var_80]
0x14005abf4  xor     r9d, r9d
0x14005abf7  mov     rax, [rcx]
0x14005abfa  lea     edx, [r9+1]
0x14005abfe  mov     rax, [rax+40h]
0x14005ac02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ac07  mov     rcx, [rbp+57h+var_80]
0x14005ac0b  mov     ebx, eax
0x14005ac0d  test    eax, eax
0x14005ac0f  jz      loc_14005AAE8
0x14005ac15  mov     rcx, [rbp+57h+var_70]
0x14005ac19  test    rcx, rcx
0x14005ac1c  jz      short loc_14005AC32
0x14005ac1e  mov     rax, [rcx]
0x14005ac21  mov     rax, [rax+10h]
0x14005ac25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ac2a  mov     [rbp+57h+var_70], 0
0x14005ac32  test    rsi, rsi
0x14005ac35  jz      short loc_14005AC49
0x14005ac37  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005ac3e  mov     r8, rsi; lpMem
0x14005ac41  xor     edx, edx; dwFlags
0x14005ac43  call    cs:__imp_HeapFree
0x14005ac49  test    ebx, ebx
0x14005ac4b  js      short loc_14005AC50
0x14005ac4d  mov     [r15], r14d
0x14005ac50  mov     eax, ebx
0x14005ac52  mov     rcx, [rbp+57h+var_28]
0x14005ac56  xor     rcx, rsp; StackCookie
0x14005ac59  call    __security_check_cookie
0x14005ac5e  mov     rbx, [rsp+0C0h+arg_10]
0x14005ac66  add     rsp, 0A0h
0x14005ac6d  pop     r15
0x14005ac6f  pop     r14
0x14005ac71  pop     rdi
0x14005ac72  pop     rsi
0x14005ac73  pop     rbp
0x14005ac74  retn
```
