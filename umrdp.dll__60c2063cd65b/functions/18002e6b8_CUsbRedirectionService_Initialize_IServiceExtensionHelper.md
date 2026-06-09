# CUsbRedirectionService::Initialize(IServiceExtensionHelper *)

- ea: `0x18002e6b8`
- end: `0x18002e81a`
- name: `?Initialize@CUsbRedirectionService@@AEAAJPEAUIServiceExtensionHelper@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(CUsbRedirectionService *__hidden this, struct IServiceExtensionHelper *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18002e568`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18002e6b8`
- `0x18002f27c`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e722`

## string_xrefs

- `0x18002e7d4`: `CUrbDrManager::CreateInstance failed`

## pseudocode

```c
__int64 __fastcall CUsbRedirectionService::Initialize(CUsbRedirectionService *this, struct IServiceExtensionHelper *a2)
{
  __int64 v3; // rax
  signed int LastError; // eax
  signed int Instance; // ebx
  int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  int v9; // edx
  unsigned int v10; // eax
  int v11; // ecx
  __int64 result; // rax
  _DWORD v13[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v14; // [rsp+38h] [rbp-30h]
  __int64 v15; // [rsp+48h] [rbp-20h]

  *((_QWORD *)this + 6) = a2;
  *((_DWORD *)this + 2) = 2;
  v14 = 0;
  v15 = 0;
  v13[0] = 32;
  v13[1] = 5;
  v3 = (**(__int64 (__fastcall ***)(struct IServiceExtensionHelper *, _DWORD *))a2)(a2, v13);
  *((_QWORD *)this + 7) = v3;
  if ( v3 )
    goto LABEL_10;
  LastError = GetLastError();
  Instance = LastError;
  if ( LastError > 0 )
    Instance = (unsigned __int16)LastError | 0x80070000;
  if ( Instance >= 0 )
  {
LABEL_10:
    Instance = CUrbDrManager::CreateInstance((struct CUrbDrManager **)this + 5);
    if ( Instance >= 0 )
    {
      *((_DWORD *)this + 2) = 4;
      Instance = 0;
    }
    else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
           && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 13;
      v8 = "CUrbDrManager::CreateInstance failed";
      goto LABEL_9;
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 12;
    v8 = "RegisterDeviceNotification failed";
LABEL_9:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v7,
      (unsigned int)WPP_aa6e4dae9cdd30cf7b6daef0f967fc22_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      Instance);
  }
  v9 = *((_DWORD *)this + 2);
  v10 = *((_DWORD *)this + 5) & 0xFFFFFFFE;
  v11 = *((_DWORD *)this + 5) | 1;
  *((_DWORD *)this + 4) = v9;
  if ( v9 != 4 )
    v11 = v10;
  result = (unsigned int)Instance;
  *((_DWORD *)this + 5) = v11;
  return result;
}

```

## disassembly

```asm
0x18002e6b8  mov     r11, rsp
0x18002e6bb  mov     [r11+10h], rbx
0x18002e6bf  push    rdi
0x18002e6c0  sub     rsp, 60h
0x18002e6c4  mov     rax, cs:__security_cookie
0x18002e6cb  xor     rax, rsp
0x18002e6ce  mov     [rsp+68h+var_18], rax
0x18002e6d3  mov     [rcx+30h], rdx
0x18002e6d7  mov     r9, rdx
0x18002e6da  mov     dword ptr [rcx+8], 2
0x18002e6e1  xorps   xmm0, xmm0
0x18002e6e4  movdqu  [rsp+68h+var_30], xmm0
0x18002e6ea  mov     qword ptr [r11-20h], 0
0x18002e6f2  mov     r8d, 5
0x18002e6f8  mov     [rsp+68h+var_38], 20h ; ' '
0x18002e700  mov     rdi, rcx
0x18002e703  mov     [r11-34h], r8d
0x18002e707  mov     rcx, r9
0x18002e70a  mov     rax, [rdx]
0x18002e70d  lea     rdx, [r11-38h]
0x18002e711  mov     rax, [rax]
0x18002e714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e719  mov     [rdi+38h], rax
0x18002e71d  test    rax, rax
0x18002e720  jnz     short loc_18002E79C
0x18002e722  call    cs:__imp_GetLastError
0x18002e728  mov     ebx, eax
0x18002e72a  test    eax, eax
0x18002e72c  jle     short loc_18002E737
0x18002e72e  movzx   ebx, ax
0x18002e731  or      ebx, 80070000h
0x18002e737  test    ebx, ebx
0x18002e739  jns     short loc_18002E79C
0x18002e73b  mov     rax, cs:WPP_GLOBAL_Control
0x18002e742  lea     rcx, WPP_GLOBAL_Control
0x18002e749  cmp     rax, rcx
0x18002e74c  jz      loc_18002E7E6
0x18002e752  test    byte ptr [rax+1Ch], 8
0x18002e756  jz      loc_18002E7E6
0x18002e75c  cmp     byte ptr [rax+19h], 2
0x18002e760  jb      loc_18002E7E6
0x18002e766  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002e76b  mov     edx, 0Ch
0x18002e770  lea     rcx, aRegisterdevice_0; "RegisterDeviceNotification failed"
0x18002e777  mov     [rsp+68h+var_40], ebx
0x18002e77b  lea     r8, WPP_aa6e4dae9cdd30cf7b6daef0f967fc22_Traceguids
0x18002e782  mov     [rsp+68h+var_48], rcx
0x18002e787  mov     r9d, eax
0x18002e78a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e791  mov     rcx, [rcx+10h]
0x18002e795  call    WPP_SF_DsD
0x18002e79a  jmp     short loc_18002E7E6
0x18002e79c  lea     rcx, [rdi+28h]; struct CUrbDrManager **
0x18002e7a0  call    ?CreateInstance@CUrbDrManager@@SAJPEAPEAV1@@Z; CUrbDrManager::CreateInstance(CUrbDrManager * *)
0x18002e7a5  mov     ebx, eax
0x18002e7a7  test    eax, eax
0x18002e7a9  jns     short loc_18002E7DD
0x18002e7ab  mov     rax, cs:WPP_GLOBAL_Control
0x18002e7b2  lea     rcx, WPP_GLOBAL_Control
0x18002e7b9  cmp     rax, rcx
0x18002e7bc  jz      short loc_18002E7E6
0x18002e7be  test    byte ptr [rax+1Ch], 8
0x18002e7c2  jz      short loc_18002E7E6
0x18002e7c4  cmp     byte ptr [rax+19h], 2
0x18002e7c8  jb      short loc_18002E7E6
0x18002e7ca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002e7cf  mov     edx, 0Dh
0x18002e7d4  lea     rcx, aCurbdrmanagerC; "CUrbDrManager::CreateInstance failed"
0x18002e7db  jmp     short loc_18002E777
0x18002e7dd  mov     dword ptr [rdi+8], 4
0x18002e7e4  xor     ebx, ebx
0x18002e7e6  mov     ecx, [rdi+14h]
0x18002e7e9  mov     eax, ecx
0x18002e7eb  mov     edx, [rdi+8]
0x18002e7ee  and     eax, 0FFFFFFFEh
0x18002e7f1  or      ecx, 1
0x18002e7f4  mov     [rdi+10h], edx
0x18002e7f7  cmp     edx, 4
0x18002e7fa  cmovnz  ecx, eax
0x18002e7fd  mov     eax, ebx
0x18002e7ff  mov     [rdi+14h], ecx
0x18002e802  mov     rcx, [rsp+68h+var_18]
0x18002e807  xor     rcx, rsp; StackCookie
0x18002e80a  call    __security_check_cookie
0x18002e80f  mov     rbx, [rsp+68h+arg_8]
0x18002e814  add     rsp, 60h
0x18002e818  pop     rdi
0x18002e819  retn
```
