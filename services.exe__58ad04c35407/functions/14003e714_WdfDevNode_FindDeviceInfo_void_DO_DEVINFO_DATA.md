# WdfDevNode::FindDeviceInfo(void * *,_DO_DEVINFO_DATA *)

- ea: `0x14003e714`
- end: `0x14003ea95`
- name: `?FindDeviceInfo@WdfDevNode@@AEAAHPEAPEAXPEAU_DO_DEVINFO_DATA@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(WdfDevNode *__hidden this, void **, struct _DO_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x14002ba14`

## callees

- `0x140004c58`
- `0x14001b928`
- `0x14001f99c`
- `0x14002db94`
- `0x14003e714`
- `0x140044300`
- `0x14008f55c`
- `0x140091f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e8ba`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14003e834`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14003e834`
- `DEVOBJ!DevObjGetClassDevs` at `0x14003e8b0`
- `DEVOBJ!DevObjGetClassDevs` at `0x14003e8b0`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14003e987`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14003e987`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x14003e944`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x14003e944`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14003ea73`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14003ea73`

## pseudocode

```c
__int64 __fastcall WdfDevNode::FindDeviceInfo(WdfDevNode *this, void **a2, struct _DO_DEVINFO_DATA *a3)
{
  const wchar_t *v3; // r15
  void **v4; // rdi
  char *v6; // r14
  __int64 v7; // rbx
  unsigned __int8 v8; // bp
  size_t v9; // rdi
  unsigned __int128 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 DeviceInfoList; // rax
  __int64 LastError; // r9
  PRPC_ASYNC_STATE v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r12d
  __int64 v18; // rdx
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  __int64 v22; // rdx
  __int64 v23; // rcx
  size_t v25; // [rsp+A0h] [rbp+8h] BYREF
  void **v26; // [rsp+A8h] [rbp+10h]

  v26 = a2;
  v3 = (const wchar_t *)*((_QWORD *)this + 9);
  v4 = a2;
  v6 = 0;
  v25 = 0;
  v7 = -1;
  v8 = 0;
  if ( StringCchLengthW(v3, 0x7FFFFFFFu, &v25) >= 0 )
  {
    v9 = v25 + 1;
    if ( v25 + 1 < v25 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 0x10) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 101, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
      }
      goto LABEL_34;
    }
    v10 = (v25 + 2) * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v25 + 2, 2u) )
      *(_QWORD *)&v10 = -1;
    v6 = (char *)operator new(v10, *((const struct std::nothrow_t **)&v10 + 1));
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 0x10) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_IS(WPP_GLOBAL_Control->u.APC.hThread, v11, v12, 2 * v9, (__int64)v3);
      }
      goto LABEL_34;
    }
    *(_WORD *)&v6[2 * v9] = 0;
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v7 = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 3u )
      {
        goto LABEL_34;
      }
      v16 = 103;
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, 0, 6, 0, 0) )
      {
        v17 = 1;
        *(_OWORD *)a3 = 0;
        v18 = 0;
        *((_OWORD *)a3 + 1) = 0;
        *((_OWORD *)a3 + 2) = 0;
        *(_DWORD *)a3 = 48;
        while ( (unsigned int)DevObjEnumDeviceInfo(v7, v18, a3) )
        {
          LODWORD(v25) = 0;
          if ( (unsigned int)DevObjGetDeviceRegistryProperty(v7, a3, 14) && (unsigned int)v25 == 2 * v9 )
          {
            v19 = (unsigned __int16 *)v6;
            do
            {
              v20 = *(unsigned __int16 *)((char *)v19 + (char *)v3 - v6);
              v21 = *v19 - v20;
              if ( v21 )
                break;
              ++v19;
            }
            while ( v20 );
            if ( !v21 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 0x10) != 0
                && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 105, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
              }
              v8 = 1;
              goto LABEL_34;
            }
          }
          v18 = v17++;
        }
        goto LABEL_34;
      }
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 3u )
      {
LABEL_34:
        v4 = v26;
        goto LABEL_35;
      }
      v16 = 104;
    }
    WPP_SF_d(v15->u.APC.hThread, v16, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, LastError);
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 0x10) != 0
    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 100, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
  }
LABEL_35:
  operator delete(v6);
  if ( v8 )
  {
    *v4 = (void *)v7;
    WudfVerify(
      v23,
      v22,
      L"minkernel\\wdf\\framework\\umdf\\drivermanager\\devnode.cpp",
      2564,
      "WdfDevNode::FindDeviceInfo");
  }
  else if ( v7 != -1 )
  {
    DevObjDestroyDeviceInfoList(v7);
  }
  return v8;
}

```

## disassembly

```asm
0x14003e714  mov     rax, rsp
0x14003e717  mov     [rax+18h], rbx
0x14003e71b  mov     [rax+10h], rdx
0x14003e71f  push    rbp
0x14003e720  push    rsi
0x14003e721  push    rdi
0x14003e722  push    r12
0x14003e724  push    r13
0x14003e726  push    r14
0x14003e728  push    r15
0x14003e72a  sub     rsp, 60h
0x14003e72e  mov     r15, [rcx+48h]
0x14003e732  mov     rdi, rdx
0x14003e735  mov     rsi, r8
0x14003e738  or      r12, 0FFFFFFFFFFFFFFFFh
0x14003e73c  xor     r14d, r14d
0x14003e73f  lea     r8, [rax+8]; pcchLength
0x14003e743  mov     rcx, r15; psz
0x14003e746  mov     [rax+8], r14
0x14003e74a  mov     edx, 7FFFFFFFh; cchMax
0x14003e74f  mov     rbx, r12
0x14003e752  xor     bpl, bpl
0x14003e755  call    StringCchLengthW
0x14003e75a  test    eax, eax
0x14003e75c  jns     short loc_14003E7A3
0x14003e75e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003e765  lea     rax, WPP_GLOBAL_Control
0x14003e76c  cmp     rcx, rax
0x14003e76f  jz      loc_14003E99D
0x14003e775  test    byte ptr [rcx+44h], 10h
0x14003e779  jz      loc_14003E99D
0x14003e77f  cmp     byte ptr [rcx+41h], 2
0x14003e783  jb      loc_14003E99D
0x14003e789  mov     rcx, [rcx+38h]
0x14003e78d  lea     edx, [r12+65h]
0x14003e792  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003e799  call    WPP_SF_
0x14003e79e  jmp     loc_14003E99D
0x14003e7a3  mov     rax, [rsp+98h+arg_0]
0x14003e7ab  lea     rdi, [rax+1]
0x14003e7af  cmp     rdi, rax
0x14003e7b2  jb      loc_14003EA26
0x14003e7b8  lea     rcx, [rdi+1]
0x14003e7bc  mov     eax, 2
0x14003e7c1  mul     rcx
0x14003e7c4  cmovb   rax, r12
0x14003e7c8  mov     rcx, rax; Size
0x14003e7cb  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14003e7d0  mov     r14, rax
0x14003e7d3  test    rax, rax
0x14003e7d6  jnz     short loc_14003E81A
0x14003e7d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003e7df  lea     rax, WPP_GLOBAL_Control
0x14003e7e6  cmp     rcx, rax
0x14003e7e9  jz      loc_14003E995
0x14003e7ef  test    byte ptr [rcx+44h], 10h
0x14003e7f3  jz      loc_14003E995
0x14003e7f9  cmp     byte ptr [rcx+41h], 2
0x14003e7fd  jb      loc_14003E995
0x14003e803  mov     rcx, [rcx+38h]
0x14003e807  lea     r9, [rdi+rdi]
0x14003e80b  mov     [rsp+98h+var_78], r15
0x14003e810  call    WPP_SF_IS
0x14003e815  jmp     loc_14003E995
0x14003e81a  xor     eax, eax
0x14003e81c  lea     r13, [rdi+rdi]
0x14003e820  xor     r9d, r9d
0x14003e823  mov     [r14+r13], ax
0x14003e828  xor     r8d, r8d
0x14003e82b  mov     [rsp+98h+var_78], rax
0x14003e830  xor     edx, edx
0x14003e832  xor     ecx, ecx
0x14003e834  call    cs:__imp_DevObjCreateDeviceInfoList
0x14003e83a  mov     rbx, rax
0x14003e83d  cmp     rax, r12
0x14003e840  jnz     short loc_14003E890
0x14003e842  call    cs:__imp_GetLastError
0x14003e848  mov     r9d, eax
0x14003e84b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003e852  lea     rax, WPP_GLOBAL_Control
0x14003e859  cmp     rcx, rax
0x14003e85c  jz      loc_14003E995
0x14003e862  test    byte ptr [rcx+44h], 1
0x14003e866  jz      loc_14003E995
0x14003e86c  cmp     byte ptr [rcx+41h], 3
0x14003e870  jb      loc_14003E995
0x14003e876  mov     edx, 67h ; 'g'
0x14003e87b  mov     rcx, [rcx+38h]
0x14003e87f  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003e886  call    WPP_SF_d
0x14003e88b  jmp     loc_14003E995
0x14003e890  mov     [rsp+98h+var_70], 0
0x14003e899  mov     r9d, 6
0x14003e89f  xor     r8d, r8d
0x14003e8a2  mov     [rsp+98h+var_78], 0
0x14003e8ab  xor     edx, edx
0x14003e8ad  mov     rcx, rbx
0x14003e8b0  call    cs:__imp_DevObjGetClassDevs
0x14003e8b6  test    eax, eax
0x14003e8b8  jnz     short loc_14003E8F5
0x14003e8ba  call    cs:__imp_GetLastError
0x14003e8c0  mov     r9d, eax
0x14003e8c3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003e8ca  lea     rax, WPP_GLOBAL_Control
0x14003e8d1  cmp     rcx, rax
0x14003e8d4  jz      loc_14003E995
0x14003e8da  test    byte ptr [rcx+44h], 1
0x14003e8de  jz      loc_14003E995
0x14003e8e4  cmp     byte ptr [rcx+41h], 3
0x14003e8e8  jb      loc_14003E995
0x14003e8ee  mov     edx, 68h ; 'h'
0x14003e8f3  jmp     short loc_14003E87B
0x14003e8f5  xorps   xmm0, xmm0
0x14003e8f8  mov     r12d, 1
0x14003e8fe  movups  xmmword ptr [rsi], xmm0
0x14003e901  xor     edx, edx
0x14003e903  movups  xmmword ptr [rsi+10h], xmm0
0x14003e907  movups  xmmword ptr [rsi+20h], xmm0
0x14003e90b  mov     dword ptr [rsi], 30h ; '0'
0x14003e911  jmp     short loc_14003E981
0x14003e913  xor     r9d, r9d
0x14003e916  mov     dword ptr [rsp+98h+arg_0], 0
0x14003e921  lea     rcx, [rsp+98h+arg_0]
0x14003e929  mov     rdx, rsi
0x14003e92c  mov     [rsp+98h+var_68], rcx
0x14003e931  lea     eax, [rdi+rdi]
0x14003e934  mov     dword ptr [rsp+98h+var_70], eax
0x14003e938  mov     rcx, rbx
0x14003e93b  lea     r8d, [r9+0Eh]
0x14003e93f  mov     [rsp+98h+var_78], r14
0x14003e944  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x14003e94a  test    eax, eax
0x14003e94c  jz      short loc_14003E97B
0x14003e94e  mov     eax, dword ptr [rsp+98h+arg_0]
0x14003e955  cmp     rax, r13
0x14003e958  jnz     short loc_14003E97B
0x14003e95a  mov     r8, r15
0x14003e95d  mov     rax, r14
0x14003e960  sub     r8, r14
0x14003e963  movzx   edx, word ptr [rax]
0x14003e966  movzx   ecx, word ptr [rax+r8]
0x14003e96b  sub     edx, ecx
0x14003e96d  jnz     short loc_14003E977
0x14003e96f  add     rax, 2
0x14003e973  test    ecx, ecx
0x14003e975  jnz     short loc_14003E963
0x14003e977  test    edx, edx
0x14003e979  jz      short loc_14003E9EA
0x14003e97b  mov     edx, r12d
0x14003e97e  inc     r12d
0x14003e981  mov     r8, rsi
0x14003e984  mov     rcx, rbx
0x14003e987  call    cs:__imp_DevObjEnumDeviceInfo
0x14003e98d  test    eax, eax
0x14003e98f  jnz     short loc_14003E913
0x14003e991  or      r12, 0FFFFFFFFFFFFFFFFh
0x14003e995  mov     rdi, [rsp+98h+arg_8]
0x14003e99d  mov     rcx, r14; void *
0x14003e9a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003e9a5  test    bpl, bpl
0x14003e9a8  jz      loc_14003EA6B
0x14003e9ae  cmp     rbx, r12
0x14003e9b1  mov     [rdi], rbx
0x14003e9b4  mov     r9d, 0A04h
0x14003e9ba  lea     r8, aMinkernelWdfFr_2; "minkernel\\wdf\\framework\\umdf\\driver"...
0x14003e9c1  setnz   al
0x14003e9c4  mov     [rsp+98h+var_50], al
0x14003e9c8  lea     rax, aFoundAMatching; "Found a matching entry, but never made "...
0x14003e9cf  mov     [rsp+98h+var_58], rax
0x14003e9d4  lea     rax, aWdfdevnodeFind; "WdfDevNode::FindDeviceInfo"
0x14003e9db  mov     [rsp+98h+var_78], rax
0x14003e9e0  call    ?WudfVerify@@YAXW4WdfComponentType@@PEAUIUMDFPlatform@@PEBGKPEBDW4WdfDriverStopType@@W4WdfErrorClass@@K3_NPEAD@Z; WudfVerify(WdfComponentType,IUMDFPlatform *,ushort const *,ulong,char const *,WdfDriverStopType,WdfErrorClass,ulong,char const *,bool,char *)
0x14003e9e5  jmp     loc_14003EA79
0x14003e9ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003e9f1  lea     rax, WPP_GLOBAL_Control
0x14003e9f8  cmp     rcx, rax
0x14003e9fb  jz      short loc_14003EA1E
0x14003e9fd  test    byte ptr [rcx+44h], 10h
0x14003ea01  jz      short loc_14003EA1E
0x14003ea03  cmp     byte ptr [rcx+41h], 5
0x14003ea07  jb      short loc_14003EA1E
0x14003ea09  mov     rcx, [rcx+38h]
0x14003ea0d  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003ea14  mov     edx, 69h ; 'i'
0x14003ea19  call    WPP_SF_
0x14003ea1e  mov     bpl, 1
0x14003ea21  jmp     loc_14003E991
0x14003ea26  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003ea2d  lea     rax, WPP_GLOBAL_Control
0x14003ea34  cmp     rcx, rax
0x14003ea37  jz      loc_14003E995
0x14003ea3d  test    byte ptr [rcx+44h], 10h
0x14003ea41  jz      loc_14003E995
0x14003ea47  cmp     byte ptr [rcx+41h], 2
0x14003ea4b  jb      loc_14003E995
0x14003ea51  mov     rcx, [rcx+38h]
0x14003ea55  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003ea5c  mov     edx, 65h ; 'e'
0x14003ea61  call    WPP_SF_
0x14003ea66  jmp     loc_14003E995
0x14003ea6b  cmp     rbx, r12
0x14003ea6e  jz      short loc_14003EA79
0x14003ea70  mov     rcx, rbx
0x14003ea73  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14003ea79  mov     rbx, [rsp+98h+arg_10]
0x14003ea81  movzx   eax, bpl
0x14003ea85  add     rsp, 60h
0x14003ea89  pop     r15
0x14003ea8b  pop     r14
0x14003ea8d  pop     r13
0x14003ea8f  pop     r12
0x14003ea91  pop     rdi
0x14003ea92  pop     rsi
0x14003ea93  pop     rbp
0x14003ea94  retn
```
