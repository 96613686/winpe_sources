# IsNetworkPPP(INetwork *,int *)

- ea: `0x1400602a4`
- end: `0x140060556`
- name: `?IsNetworkPPP@@YAJPEAUINetwork@@PEAH@Z`
- size: `690`
- prototype: `__int64 __fastcall(struct INetwork *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14005ff8c`

## callees

- `0x140004790`
- `0x14002d0a0`
- `0x1400602a4`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x14006045f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x14006045f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006038a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006051d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006038a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006051d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060430`
- `KERNEL32!WideCharToMultiByte` at `0x140060420`
- `KERNEL32!WideCharToMultiByte` at `0x140060420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400604aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400604aa`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400603e3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400603e3`
- `IPHLPAPI!GetAdaptersAddresses` at `0x14006035b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x14006035b`

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
0x1400602a4  mov     [rsp-8+arg_10], rbx
0x1400602a9  push    rbp
0x1400602aa  push    rsi
0x1400602ab  push    rdi
0x1400602ac  push    r14
0x1400602ae  push    r15
0x1400602b0  lea     rbp, [rsp-37h]
0x1400602b5  sub     rsp, 0A0h
0x1400602bc  mov     rax, cs:__security_cookie
0x1400602c3  xor     rax, rsp
0x1400602c6  mov     [rbp+57h+var_28], rax
0x1400602ca  mov     r15, rdx
0x1400602cd  mov     [rbp+57h+var_70], 0
0x1400602d5  xor     esi, esi
0x1400602d7  mov     [rbp+57h+var_80], 0
0x1400602df  mov     [rdx], esi
0x1400602e1  xor     r14d, r14d
0x1400602e4  mov     rax, [rcx]
0x1400602e7  lea     rdx, [rbp+57h+var_70]
0x1400602eb  mov     [rbp+57h+var_78], 2710h
0x1400602f2  mov     rax, [rax+68h]
0x1400602f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400602fb  mov     ebx, eax
0x1400602fd  test    eax, eax
0x1400602ff  js      short loc_14006031D
0x140060301  mov     rcx, [rbp+57h+var_70]
0x140060305  lea     r8, [rbp+57h+var_80]
0x140060309  xor     r9d, r9d
0x14006030c  lea     edx, [rsi+1]
0x14006030f  mov     rax, [rcx]
0x140060312  mov     rax, [rax+40h]
0x140060316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006031b  mov     ebx, eax
0x14006031d  test    ebx, ebx
0x14006031f  jnz     loc_1400604EF
0x140060325  mov     rcx, [rbp+57h+var_80]
0x140060329  test    rcx, rcx
0x14006032c  jz      loc_1400604EF
0x140060332  mov     ecx, [rbp+57h+var_78]; dwBytes
0x140060335  call    DllAllocSplMem
0x14006033a  mov     rsi, rax
0x14006033d  test    rax, rax
0x140060340  jz      loc_14006047B
0x140060346  xor     r8d, r8d; Reserved
0x140060349  lea     rax, [rbp+57h+var_78]
0x14006034d  mov     r9, rsi; AdapterAddresses
0x140060350  mov     [rsp+0C0h+SizePointer], rax; SizePointer
0x140060355  xor     ecx, ecx; Family
0x140060357  lea     edx, [r8+2Fh]; Flags
0x14006035b  call    cs:__imp_GetAdaptersAddresses
0x140060362  nop     dword ptr [rax+rax+00h]
0x140060367  mov     ebx, eax
0x140060369  test    eax, eax
0x14006036b  jle     short loc_140060376
0x14006036d  movzx   ebx, ax
0x140060370  or      ebx, 80070000h
0x140060376  cmp     ebx, 8007006Fh
0x14006037c  jnz     short loc_140060398
0x14006037e  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140060385  mov     r8, rsi; lpMem
0x140060388  xor     edx, edx; dwFlags
0x14006038a  call    cs:__imp_HeapFree
0x140060391  nop     dword ptr [rax+rax+00h]
0x140060396  jmp     short loc_140060332
0x140060398  test    ebx, ebx
0x14006039a  jnz     loc_1400604EF
0x1400603a0  mov     rcx, [rbp+57h+var_80]
0x1400603a4  test    rcx, rcx
0x1400603a7  jz      loc_1400604EF
0x1400603ad  test    r14d, r14d
0x1400603b0  jnz     loc_1400604EF
0x1400603b6  xorps   xmm0, xmm0
0x1400603b9  mov     [rbp+57h+lpsz], 0
0x1400603c1  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x1400603c5  mov     rax, [rcx]
0x1400603c8  lea     rdx, [rbp+57h+rclsid]
0x1400603cc  mov     rax, [rax+60h]
0x1400603d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400603d5  mov     ebx, eax
0x1400603d7  test    eax, eax
0x1400603d9  js      short loc_1400603F1
0x1400603db  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1400603df  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1400603e3  call    cs:__imp_StringFromCLSID
0x1400603ea  nop     dword ptr [rax+rax+00h]
0x1400603ef  mov     ebx, eax
0x1400603f1  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x1400603f5  lea     rax, [rbp+57h+MultiByteStr]
0x1400603f9  mov     [rsp+0C0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140060402  or      r9d, 0FFFFFFFFh; cchWideChar
0x140060406  mov     [rsp+0C0h+lpDefaultChar], 0; lpDefaultChar
0x14006040f  xor     edx, edx; dwFlags
0x140060411  mov     [rsp+0C0h+cbMultiByte], 28h ; '('; cbMultiByte
0x140060419  xor     ecx, ecx; CodePage
0x14006041b  mov     [rsp+0C0h+SizePointer], rax; lpMultiByteStr
0x140060420  call    cs:__imp_WideCharToMultiByte
0x140060427  nop     dword ptr [rax+rax+00h]
0x14006042c  test    eax, eax
0x14006042e  jnz     short loc_14006044B
0x140060430  call    cs:__imp_GetLastError
0x140060437  nop     dword ptr [rax+rax+00h]
0x14006043c  mov     ebx, eax
0x14006043e  test    eax, eax
0x140060440  jle     short loc_14006044B
0x140060442  movzx   ebx, ax
0x140060445  or      ebx, 80070000h
0x14006044b  test    ebx, ebx
0x14006044d  js      short loc_140060488
0x14006044f  mov     rdi, rsi
0x140060452  test    rdi, rdi
0x140060455  jz      short loc_140060488
0x140060457  mov     rcx, [rdi+10h]
0x14006045b  lea     rdx, [rbp+57h+MultiByteStr]
0x14006045f  call    cs:__imp__o__stricmp
0x140060466  nop     dword ptr [rax+rax+00h]
0x14006046b  test    eax, eax
0x14006046d  jnz     short loc_140060475
0x14006046f  cmp     dword ptr [rdi+64h], 17h
0x140060473  jz      short loc_140060482
0x140060475  mov     rdi, [rdi+8]
0x140060479  jmp     short loc_140060452
0x14006047b  mov     ebx, 8007000Eh
0x140060480  jmp     short loc_1400604EF
0x140060482  mov     r14d, 1
0x140060488  mov     rcx, [rbp+57h+var_80]
0x14006048c  mov     rax, [rcx]
0x14006048f  mov     rax, [rax+10h]
0x140060493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060498  mov     rax, [rbp+57h+lpsz]
0x14006049c  xor     ecx, ecx
0x14006049e  mov     [rbp+57h+var_80], rcx
0x1400604a2  test    rax, rax
0x1400604a5  jz      short loc_1400604C2
0x1400604a7  mov     rcx, rax; pv
0x1400604aa  call    cs:__imp_CoTaskMemFree
0x1400604b1  nop     dword ptr [rax+rax+00h]
0x1400604b6  mov     rcx, [rbp+57h+var_80]
0x1400604ba  mov     [rbp+57h+lpsz], 0
0x1400604c2  test    ebx, ebx
0x1400604c4  js      short loc_1400604E9
0x1400604c6  mov     rcx, [rbp+57h+var_70]
0x1400604ca  lea     r8, [rbp+57h+var_80]
0x1400604ce  xor     r9d, r9d
0x1400604d1  mov     rax, [rcx]
0x1400604d4  lea     edx, [r9+1]
0x1400604d8  mov     rax, [rax+40h]
0x1400604dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400604e1  mov     rcx, [rbp+57h+var_80]
0x1400604e5  mov     ebx, eax
0x1400604e7  test    eax, eax
0x1400604e9  jz      loc_1400603A4
0x1400604ef  mov     rcx, [rbp+57h+var_70]
0x1400604f3  test    rcx, rcx
0x1400604f6  jz      short loc_14006050C
0x1400604f8  mov     rax, [rcx]
0x1400604fb  mov     rax, [rax+10h]
0x1400604ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060504  mov     [rbp+57h+var_70], 0
0x14006050c  test    rsi, rsi
0x14006050f  jz      short loc_140060529
0x140060511  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140060518  mov     r8, rsi; lpMem
0x14006051b  xor     edx, edx; dwFlags
0x14006051d  call    cs:__imp_HeapFree
0x140060524  nop     dword ptr [rax+rax+00h]
0x140060529  test    ebx, ebx
0x14006052b  js      short loc_140060530
0x14006052d  mov     [r15], r14d
0x140060530  mov     eax, ebx
0x140060532  mov     rcx, [rbp+57h+var_28]
0x140060536  xor     rcx, rsp; StackCookie
0x140060539  call    __security_check_cookie
0x14006053e  mov     rbx, [rsp+0C0h+arg_10]
0x140060546  add     rsp, 0A0h
0x14006054d  pop     r15
0x14006054f  pop     r14
0x140060551  pop     rdi
0x140060552  pop     rsi
0x140060553  pop     rbp
0x140060554  retn
```
