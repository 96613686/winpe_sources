# NotificationServiceImpl::InitKADetectorRegistrationTimer(void)

- ea: `0x18006e724`
- end: `0x18006e8d4`
- name: `?InitKADetectorRegistrationTimer@NotificationServiceImpl@@AEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c720`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x18006e724`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e83d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e83d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e7ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e7ac`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::InitKADetectorRegistrationTimer(NotificationServiceImpl *this)
{
  unsigned int v2; // ebx
  bool v3; // cf
  int v4; // eax
  __int64 v5; // r9
  PVOID *v6; // rcx
  unsigned int v8; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  v2 = 0;
  v3 = *((_DWORD *)this + 24) != 0;
  hKey = 0;
  v8 = 0;
  *((_DWORD *)this + 46) = v3 ? 240 : 60;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_12;
  }
  v4 = WpnRegLoadDWord(hKey, L"KADetectorDelay", &v8);
  v2 = v4;
  if ( v4 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v4);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v2 = 0;
  }
  else
  {
    if ( v8 )
    {
      *((_DWORD *)this + 46) = v8;
      goto LABEL_12;
    }
    v5 = *((_DWORD *)this + 24) != 0 ? 240 : 60;
    *((_DWORD *)this + 46) = v5;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v5);
LABEL_12:
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 253, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18006e724  mov     [rsp+arg_10], rbx
0x18006e729  mov     [rsp+arg_18], rbp
0x18006e72e  push    rdi
0x18006e72f  sub     rsp, 30h
0x18006e733  mov     rdi, rcx
0x18006e736  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e73d  lea     rbp, WPP_GLOBAL_Control
0x18006e744  cmp     rcx, rbp
0x18006e747  jz      short loc_18006E76A
0x18006e749  test    byte ptr [rcx+1Ch], 2
0x18006e74d  jz      short loc_18006E76A
0x18006e74f  cmp     byte ptr [rcx+19h], 6
0x18006e753  jb      short loc_18006E76A
0x18006e755  mov     rcx, [rcx+10h]
0x18006e759  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e760  mov     edx, 0FAh
0x18006e765  call    WPP_SF_
0x18006e76a  mov     eax, [rdi+60h]
0x18006e76d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006e774  xor     ebx, ebx
0x18006e776  mov     r9d, 20019h; samDesired
0x18006e77c  neg     eax
0x18006e77e  mov     [rsp+38h+hKey], rbx
0x18006e783  lea     rax, [rsp+38h+hKey]
0x18006e788  mov     [rsp+38h+arg_0], ebx
0x18006e78c  sbb     ecx, ecx
0x18006e78e  mov     [rsp+38h+phkResult], rax; phkResult
0x18006e793  and     ecx, 0B4h
0x18006e799  xor     r8d, r8d; ulOptions
0x18006e79c  add     ecx, 3Ch ; '<'
0x18006e79f  mov     [rdi+0B8h], ecx
0x18006e7a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e7ac  call    cs:__imp_RegOpenKeyExW
0x18006e7b2  test    eax, eax
0x18006e7b4  jnz     short loc_18006E829
0x18006e7b6  mov     rcx, [rsp+38h+hKey]; hKey
0x18006e7bb  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18006e7c0  lea     rdx, aKadetectordela; "KADetectorDelay"
0x18006e7c7  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18006e7cc  mov     ebx, eax
0x18006e7ce  test    eax, eax
0x18006e7d0  js      loc_18006E896
0x18006e7d6  mov     eax, [rsp+38h+arg_0]
0x18006e7da  test    eax, eax
0x18006e7dc  jnz     loc_18006E88E
0x18006e7e2  mov     ecx, [rdi+60h]
0x18006e7e5  neg     ecx
0x18006e7e7  sbb     r9d, r9d
0x18006e7ea  and     r9d, 0B4h
0x18006e7f1  add     r9d, 3Ch ; '<'
0x18006e7f5  mov     [rdi+0B8h], r9d
0x18006e7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e803  cmp     rcx, rbp
0x18006e806  jz      short loc_18006E830
0x18006e808  test    byte ptr [rcx+1Ch], 4
0x18006e80c  jz      short loc_18006E830
0x18006e80e  cmp     byte ptr [rcx+19h], 5
0x18006e812  jb      short loc_18006E830
0x18006e814  mov     rcx, [rcx+10h]
0x18006e818  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e81f  mov     edx, 0FBh
0x18006e824  call    WPP_SF_d
0x18006e829  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e830  mov     rax, [rsp+38h+hKey]
0x18006e835  test    rax, rax
0x18006e838  jz      short loc_18006E853
0x18006e83a  mov     rcx, rax; hKey
0x18006e83d  call    cs:__imp_RegCloseKey
0x18006e843  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e84a  mov     [rsp+38h+hKey], 0
0x18006e853  cmp     rcx, rbp
0x18006e856  jz      short loc_18006E87C
0x18006e858  test    byte ptr [rcx+1Ch], 2
0x18006e85c  jz      short loc_18006E87C
0x18006e85e  cmp     byte ptr [rcx+19h], 6
0x18006e862  jb      short loc_18006E87C
0x18006e864  mov     rcx, [rcx+10h]
0x18006e868  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e86f  mov     edx, 0FDh
0x18006e874  mov     r9d, ebx
0x18006e877  call    WPP_SF_d
0x18006e87c  mov     rbp, [rsp+38h+arg_18]
0x18006e881  mov     eax, ebx
0x18006e883  mov     rbx, [rsp+38h+arg_10]
0x18006e888  add     rsp, 30h
0x18006e88c  pop     rdi
0x18006e88d  retn
0x18006e88e  mov     [rdi+0B8h], eax
0x18006e894  jmp     short loc_18006E829
0x18006e896  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e89d  cmp     rcx, rbp
0x18006e8a0  jz      short loc_18006E8CD
0x18006e8a2  test    byte ptr [rcx+1Ch], 2
0x18006e8a6  jz      short loc_18006E8CD
0x18006e8a8  cmp     byte ptr [rcx+19h], 3
0x18006e8ac  jb      short loc_18006E8CD
0x18006e8ae  mov     rcx, [rcx+10h]
0x18006e8b2  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e8b9  mov     edx, 0FCh
0x18006e8be  mov     r9d, eax
0x18006e8c1  call    WPP_SF_d
0x18006e8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e8cd  xor     ebx, ebx
0x18006e8cf  jmp     loc_18006E830
```
