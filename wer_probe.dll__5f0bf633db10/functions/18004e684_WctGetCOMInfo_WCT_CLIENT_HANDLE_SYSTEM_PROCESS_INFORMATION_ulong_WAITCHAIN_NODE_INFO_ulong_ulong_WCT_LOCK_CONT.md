# WctGetCOMInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *,_WCT_LOCK_CONTEXT *)

- ea: `0x18004e684`
- end: `0x18004e96c`
- name: `?WctGetCOMInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@KPEAU_WAITCHAIN_NODE_INFO@@PEAK3PEAU_WCT_LOCK_CONTEXT@@@Z`
- size: `744`
- prototype: `unsigned int __usercall@<eax>(struct _WCT_CLIENT_HANDLE *@<rcx>, struct _SYSTEM_PROCESS_INFORMATION *@<rdx>, unsigned int@<r8d>, struct _WAITCHAIN_NODE_INFO *@<r9>, unsigned int *, unsigned int *, struct _WCT_LOCK_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18004e684`
- `0x180050db0`
- `0x18005b8d1`
- `0x18005cf40`
- `0x18005ee40`
- `0x18005efd4`
- `0x1800aa084`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18004e753`
- `ntdll!NtQueryInformationThread` at `0x18004e753`
- `ntdll!RtlStringFromGUID` at `0x18004e84d`
- `ntdll!RtlStringFromGUID` at `0x18004e84d`
- `ntdll!RtlFreeUnicodeString` at `0x18004e88d`
- `ntdll!RtlFreeUnicodeString` at `0x18004e88d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004e78d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004e7c3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004e81d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004e78d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004e7c3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004e81d`

## pseudocode

```c
__int64 __fastcall WctGetCOMInfo(
        HANDLE *a1,
        struct _SYSTEM_PROCESS_INFORMATION *a2,
        char a3,
        struct _WAITCHAIN_NODE_INFO *a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _WCT_LOCK_CONTEXT *a7)
{
  unsigned int v10; // eax
  unsigned __int64 Length; // rbx
  int v12; // ebx
  GUID v13; // xmm0
  unsigned int v14; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-71h] BYREF
  __int64 v17; // [rsp+38h] [rbp-69h] BYREF
  __int64 Buffer; // [rsp+40h] [rbp-61h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-59h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+58h] [rbp-49h] BYREF
  struct _SYSTEM_PROCESS_INFORMATION *v21; // [rsp+60h] [rbp-41h]
  _OWORD ThreadInformation[3]; // [rsp+68h] [rbp-39h] BYREF
  __int128 Buf1; // [rsp+98h] [rbp-9h] BYREF

  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  Buffer = 0;
  v17 = 0;
  Buf1 = 0;
  v21 = a2;
  GuidString = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  if ( dword_1800D9CA0
    && !(unsigned int)WctIsWow64(a1[1])
    && NtQueryInformationThread(*a1, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength) >= 0
    && ReturnLength == 48
    && ReadProcessMemory(
         a1[1],
         (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 5976LL),
         &Buffer,
         8u,
         &NumberOfBytesRead)
    && NumberOfBytesRead == 8
    && ReadProcessMemory(a1[1], (LPCVOID)(Buffer + (unsigned int)dword_1800D9CA0), &v17, 8u, 0)
    && HIDWORD(v17) != -1 )
  {
    v10 = dword_1800D9C88;
    a4->ObjectType = WctComType;
    a4->ObjectStatus = WctStatusOwned;
    Buf1 = xmmword_1800B5730;
    if ( v10 )
    {
      if ( ReadProcessMemory(a1[1], (LPCVOID)(Buffer + v10), &Buf1, 0x10u, 0) )
      {
        if ( memcmp_0(&Buf1, &xmmword_1800B5730, 0x10u) )
        {
          GuidString.Buffer = 0;
          if ( RtlStringFromGUID((const GUID *const)&Buf1, &GuidString) >= 0 )
          {
            if ( GuidString.Length < 0x100u )
            {
              Length = GuidString.Length;
              memcpy_0(&a4->LockObject, GuidString.Buffer, GuidString.Length);
              a4->LockObject.ObjectName[Length >> 1] = 0;
            }
            if ( GuidString.Buffer )
              RtlFreeUnicodeString(&GuidString);
          }
        }
      }
    }
    *a5 = HIDWORD(v17);
    if ( (_DWORD)v17 )
    {
      *a6 = v17;
    }
    else
    {
      *a6 = 0;
      *a5 = 0;
    }
    v12 = *a6;
    if ( *a6 != *((_DWORD *)a1 + 4) )
    {
      if ( !memcmp_0(&Buf1, &xmmword_1800B5730, 0x10u) || !(unsigned int)WctIsRpcssPid(v12) )
      {
        if ( !*a5 && (a3 & 2) != 0 )
          WctGetCOMServerInfo((struct _WCT_CLIENT_HANDLE *)a1, v21, a5, a6);
      }
      else
      {
        v13 = (GUID)Buf1;
        *(_DWORD *)a7 = 9;
        *(GUID *)((char *)a7 + 4) = v13;
      }
    }
    v14 = 0;
  }
  else
  {
    v14 = 1168;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_4c32fa7a72a13340317baef891270170_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18004e684  mov     [rsp-8+arg_10], rbx
0x18004e689  push    rbp
0x18004e68a  push    rsi
0x18004e68b  push    rdi
0x18004e68c  push    r12
0x18004e68e  push    r13
0x18004e690  push    r14
0x18004e692  push    r15
0x18004e694  lea     rbp, [rsp-0Fh]
0x18004e699  sub     rsp, 0B0h
0x18004e6a0  mov     rax, cs:__security_cookie
0x18004e6a7  xor     rax, rsp
0x18004e6aa  mov     [rbp+3Fh+var_38], rax
0x18004e6ae  mov     r12, [rbp+3Fh+arg_30]
0x18004e6b2  xorps   xmm0, xmm0
0x18004e6b5  mov     rsi, [rbp+3Fh+arg_20]
0x18004e6b9  xor     ebx, ebx
0x18004e6bb  mov     r14, [rbp+3Fh+arg_28]
0x18004e6bf  xorps   xmm1, xmm1
0x18004e6c2  movups  [rbp+3Fh+ThreadInformation], xmm0
0x18004e6c6  mov     [rbp+3Fh+NumberOfBytesRead], rbx
0x18004e6ca  mov     r15, r9
0x18004e6cd  movups  [rbp+3Fh+var_68], xmm0
0x18004e6d1  mov     [rbp+3Fh+var_B0], ebx
0x18004e6d4  mov     r13d, r8d
0x18004e6d7  movups  [rbp+3Fh+var_58], xmm0
0x18004e6db  mov     [rbp+3Fh+Buffer], rbx
0x18004e6df  mov     rdi, rcx
0x18004e6e2  mov     [rbp+3Fh+var_A8], rbx
0x18004e6e6  movups  [rbp+3Fh+Buf1], xmm0
0x18004e6ea  mov     [rbp+3Fh+var_80], rdx
0x18004e6ee  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm1
0x18004e6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e6f9  lea     rax, WPP_GLOBAL_Control
0x18004e700  cmp     rcx, rax
0x18004e703  jz      short loc_18004E71E
0x18004e705  test    byte ptr [rcx+1Ch], 4
0x18004e709  jz      short loc_18004E71E
0x18004e70b  mov     rcx, [rcx+10h]
0x18004e70f  lea     edx, [rbx+26h]
0x18004e712  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18004e719  call    WPP_SF_
0x18004e71e  cmp     cs:dword_1800D9CA0, ebx
0x18004e724  jz      loc_18004E90D
0x18004e72a  mov     rcx, [rdi+8]; void *
0x18004e72e  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18004e733  test    eax, eax
0x18004e735  jnz     loc_18004E90D
0x18004e73b  mov     rcx, [rdi]; ThreadHandle
0x18004e73e  lea     rax, [rbp+3Fh+var_B0]
0x18004e742  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18004e748  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18004e74d  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x18004e751  xor     edx, edx; ThreadInformationClass
0x18004e753  call    cs:__imp_NtQueryInformationThread
0x18004e759  test    eax, eax
0x18004e75b  js      loc_18004E90D
0x18004e761  cmp     [rbp+3Fh+var_B0], 30h ; '0'
0x18004e765  jnz     loc_18004E90D
0x18004e76b  mov     rdx, qword ptr [rbp+3Fh+ThreadInformation+8]
0x18004e76f  lea     rax, [rbp+3Fh+NumberOfBytesRead]
0x18004e773  mov     rcx, [rdi+8]; hProcess
0x18004e777  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x18004e77b  add     rdx, 1758h; lpBaseAddress
0x18004e782  mov     [rsp+0E0h+ReturnLength], rax; lpNumberOfBytesRead
0x18004e787  mov     r9d, 8; nSize
0x18004e78d  call    cs:__imp_ReadProcessMemory
0x18004e793  test    eax, eax
0x18004e795  jz      loc_18004E90D
0x18004e79b  cmp     [rbp+3Fh+NumberOfBytesRead], 8
0x18004e7a0  jnz     loc_18004E90D
0x18004e7a6  mov     edx, cs:dword_1800D9CA0
0x18004e7ac  lea     r8, [rbp+3Fh+var_A8]; lpBuffer
0x18004e7b0  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x18004e7b4  mov     r9d, 8; nSize
0x18004e7ba  mov     rcx, [rdi+8]; hProcess
0x18004e7be  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x18004e7c3  call    cs:__imp_ReadProcessMemory
0x18004e7c9  test    eax, eax
0x18004e7cb  jz      loc_18004E90D
0x18004e7d1  cmp     dword ptr [rbp+3Fh+var_A8+4], 0FFFFFFFFh
0x18004e7d5  jz      loc_18004E90D
0x18004e7db  mov     eax, cs:dword_1800D9C88
0x18004e7e1  mov     dword ptr [r15], 5
0x18004e7e8  mov     dword ptr [r15+4], 6
0x18004e7f0  movups  xmm0, cs:xmmword_1800B5730
0x18004e7f7  movdqu  [rbp+3Fh+Buf1], xmm0
0x18004e7fc  test    eax, eax
0x18004e7fe  jz      loc_18004E893
0x18004e804  mov     rcx, [rdi+8]; hProcess
0x18004e808  lea     r8, [rbp+3Fh+Buf1]; lpBuffer
0x18004e80c  mov     edx, eax
0x18004e80e  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x18004e813  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x18004e817  mov     r9d, 10h; nSize
0x18004e81d  call    cs:__imp_ReadProcessMemory
0x18004e823  test    eax, eax
0x18004e825  jz      short loc_18004E893
0x18004e827  mov     r8d, 10h; Size
0x18004e82d  lea     rdx, xmmword_1800B5730; Buf2
0x18004e834  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18004e838  call    memcmp_0
0x18004e83d  test    eax, eax
0x18004e83f  jz      short loc_18004E893
0x18004e841  lea     rdx, [rbp+3Fh+GuidString]; GuidString
0x18004e845  mov     [rbp+3Fh+GuidString.Buffer], rbx
0x18004e849  lea     rcx, [rbp+3Fh+Buf1]; Guid
0x18004e84d  call    cs:__imp_RtlStringFromGUID
0x18004e853  test    eax, eax
0x18004e855  js      short loc_18004E893
0x18004e857  mov     eax, 100h
0x18004e85c  cmp     [rbp+3Fh+GuidString.Length], ax
0x18004e860  jnb     short loc_18004E883
0x18004e862  movzx   ebx, [rbp+3Fh+GuidString.Length]
0x18004e866  lea     rcx, [r15+8]; void *
0x18004e86a  mov     rdx, [rbp+3Fh+GuidString.Buffer]; Src
0x18004e86e  mov     r8d, ebx; Size
0x18004e871  call    memcpy_0
0x18004e876  shr     rbx, 1
0x18004e879  xor     eax, eax
0x18004e87b  mov     [r15+rbx*2+8], ax
0x18004e881  xor     ebx, ebx
0x18004e883  cmp     [rbp+3Fh+GuidString.Buffer], rbx
0x18004e887  jz      short loc_18004E893
0x18004e889  lea     rcx, [rbp+3Fh+GuidString]; UnicodeString
0x18004e88d  call    cs:__imp_RtlFreeUnicodeString
0x18004e893  mov     eax, dword ptr [rbp+3Fh+var_A8+4]
0x18004e896  mov     [rsi], eax
0x18004e898  mov     rax, [rbp+3Fh+var_A8]
0x18004e89c  test    eax, eax
0x18004e89e  jnz     short loc_18004E8A7
0x18004e8a0  mov     [r14], ebx
0x18004e8a3  mov     [rsi], ebx
0x18004e8a5  jmp     short loc_18004E8AA
0x18004e8a7  mov     [r14], eax
0x18004e8aa  mov     ebx, [r14]
0x18004e8ad  cmp     ebx, [rdi+10h]
0x18004e8b0  jz      short loc_18004E909
0x18004e8b2  mov     r8d, 10h; Size
0x18004e8b8  lea     rdx, xmmword_1800B5730; Buf2
0x18004e8bf  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18004e8c3  call    memcmp_0
0x18004e8c8  test    eax, eax
0x18004e8ca  jz      short loc_18004E8EC
0x18004e8cc  mov     ecx, ebx; unsigned int
0x18004e8ce  call    ?WctIsRpcssPid@@YAHK@Z; WctIsRpcssPid(ulong)
0x18004e8d3  test    eax, eax
0x18004e8d5  jz      short loc_18004E8EC
0x18004e8d7  movups  xmm0, [rbp+3Fh+Buf1]
0x18004e8db  mov     dword ptr [r12], 9
0x18004e8e3  movdqu  xmmword ptr [r12+4], xmm0
0x18004e8ea  jmp     short loc_18004E909
0x18004e8ec  cmp     dword ptr [rsi], 0
0x18004e8ef  jnz     short loc_18004E909
0x18004e8f1  test    r13b, 2
0x18004e8f5  jz      short loc_18004E909
0x18004e8f7  mov     rdx, [rbp+3Fh+var_80]; struct _SYSTEM_PROCESS_INFORMATION *
0x18004e8fb  mov     r9, r14; unsigned int *
0x18004e8fe  mov     r8, rsi; unsigned int *
0x18004e901  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x18004e904  call    ?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z; WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)
0x18004e909  xor     ebx, ebx
0x18004e90b  jmp     short loc_18004E912
0x18004e90d  mov     ebx, 490h
0x18004e912  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e919  lea     rax, WPP_GLOBAL_Control
0x18004e920  cmp     rcx, rax
0x18004e923  jz      short loc_18004E943
0x18004e925  test    byte ptr [rcx+1Ch], 4
0x18004e929  jz      short loc_18004E943
0x18004e92b  mov     rcx, [rcx+10h]
0x18004e92f  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18004e936  mov     edx, 27h ; '''
0x18004e93b  mov     r9d, ebx
0x18004e93e  call    WPP_SF_d
0x18004e943  mov     eax, ebx
0x18004e945  mov     rcx, [rbp+3Fh+var_38]
0x18004e949  xor     rcx, rsp; StackCookie
0x18004e94c  call    __security_check_cookie
0x18004e951  mov     rbx, [rsp+0E0h+arg_10]
0x18004e959  add     rsp, 0B0h
0x18004e960  pop     r15
0x18004e962  pop     r14
0x18004e964  pop     r13
0x18004e966  pop     r12
0x18004e968  pop     rdi
0x18004e969  pop     rsi
0x18004e96a  pop     rbp
0x18004e96b  retn
```
