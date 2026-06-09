# DeviceInfoSet::RegisterDeviceNotificationW(CSimpleStringBase<ushort> const &,void *,ulong)

- ea: `0x180011f6c`
- end: `0x180012327`
- name: `?RegisterDeviceNotificationW@DeviceInfoSet@@QEAAXAEBV?$CSimpleStringBase@G@@PEAXK@Z`
- size: `955`
- prototype: `void __fastcall(__int64, __int64, void *, DWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006d20`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x180010f0c`
- `0x180011f6c`
- `0x180012f64`
- `0x18002c868`
- `0x18002c8b0`
- `0x180033878`
- `0x180033cc0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800121b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800121b8`
- `KERNEL32!GetLastError` at `0x18001209c`
- `KERNEL32!GetLastError` at `0x180012133`
- `KERNEL32!GetLastError` at `0x180012231`
- `KERNEL32!GetLastError` at `0x18001224d`
- `KERNEL32!GetLastError` at `0x18001228d`
- `KERNEL32!GetLastError` at `0x18001209c`
- `KERNEL32!GetLastError` at `0x180012133`
- `KERNEL32!GetLastError` at `0x180012231`
- `KERNEL32!GetLastError` at `0x18001224d`
- `KERNEL32!GetLastError` at `0x18001228d`
- `KERNEL32!CloseHandle` at `0x18001223c`
- `KERNEL32!CloseHandle` at `0x18001223c`
- `USER32!RegisterDeviceNotificationW` at `0x18001221d`
- `USER32!RegisterDeviceNotificationW` at `0x18001221d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012050`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012050`

## string_xrefs

- `0x1800120c0`: `The DeviceInfoSet could not open the interface (%ws) on device (%ws).  Error = 0x%08X`
- `0x180012158`: `The DeviceInfoSet could not open the interface (%ws) on device (%ws).  Error = 0x%08X`
- `0x18001225a`: `Attempt to register for PnP notifications on device (%ws) failed. Error:0x%X`
- `0x18001229a`: `Attempt to register for PnP notifications on device (%ws) failed. Error:0x%X`

## pseudocode

```c
void __fastcall DeviceInfoSet::RegisterDeviceNotificationW(__int64 a1, __int64 a2, void *a3, DWORD a4)
{
  int v8; // eax
  HANDLE *v9; // rbx
  int v10; // r13d
  __int64 v11; // rax
  __int64 InterfaceName; // rax
  HANDLE FileW; // rax
  unsigned __int64 v14; // rdx
  char *v15; // rcx
  DWORD LastError; // eax
  __int64 v17; // rbx
  DWORD v18; // edi
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  char *v21; // rbx
  void *v22; // rdx
  DWORD v23; // eax
  __int64 v24; // rdi
  DWORD v25; // ebx
  __int64 v26; // rax
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  char *v31; // rax
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  char *v37; // rbx
  void *v38; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  __int128 NotificationFilter; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h]
  __int128 v45; // [rsp+60h] [rbp-A0h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  const unsigned __int64 *v47; // [rsp+80h] [rbp-80h] BYREF
  char v48; // [rsp+88h] [rbp-78h] BYREF
  void *v49; // [rsp+188h] [rbp+88h]
  __int64 v50; // [rsp+190h] [rbp+90h]
  const unsigned __int64 *v51; // [rsp+1B0h] [rbp+B0h] BYREF
  char v52; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v53; // [rsp+2B8h] [rbp+1B8h]
  const unsigned __int64 *v54; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v55; // [rsp+2E8h] [rbp+1E8h] BYREF
  void *v56; // [rsp+3E8h] [rbp+2E8h]

  v8 = CRIT_SECT::Lock((CRIT_SECT *)(a1 + 56));
  v9 = *(HANDLE **)(a1 + 32);
  v10 = v8;
  while ( v9 )
  {
    if ( (unsigned __int8)operator==(v9 + 2, a2) )
    {
      if ( (((unsigned __int64)v9[49] + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v46 = 0;
        v11 = (__int64)v9[48] + 1;
        NotificationFilter = 0;
        *(_OWORD *)hObject = 0;
        v45 = 0;
        if ( (v11 & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          InterfaceName = DeviceInfoSet::GetInterfaceName(a1, &v51, a2);
          FileW = CreateFileW(*(LPCWSTR *)(InterfaceName + 264), 0x80000000, 0, 0, 3u, 0, 0);
          v15 = (char *)v53;
          v9[48] = FileW;
          v51 = &CSimpleStringBase<unsigned short>::`vftable';
          if ( v15 )
          {
            if ( v15 != &v52 )
              operator delete(v15, v14);
          }
        }
        if ( (char *)v9[48] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          hObject[0] = v9[48];
          LODWORD(NotificationFilter) = 56;
          *(_QWORD *)((char *)&NotificationFilter + 4) = 6;
          v31 = (char *)RegisterDeviceNotificationW(a3, &NotificationFilter, a4);
          if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            v9[49] = v31;
            v37 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                            4,
                            0,
                            "Registered for PnP notifications on device (%ws)",
                            *(_QWORD *)(a2 + 264));
            WriteDbgTraceInfoWI("DeviceInfoSet::RegisterDeviceNotificationW", v37);
            WiaTrcLib::Free((WiaTrcLib *)v37, v38);
            v34 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                             4,
                             0,
                             "Registered for PnP notifications on device (%ws)",
                             *(_QWORD *)(a2 + 264));
          }
          else
          {
            GetLastError();
            CloseHandle(hObject[0]);
            v9[48] = 0;
            dwCreationDisposition[0] = GetLastError();
            v32 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                            4,
                            0,
                            "Attempt to register for PnP notifications on device (%ws) failed. Error:0x%X",
                            *(_QWORD *)(a2 + 264),
                            *(_QWORD *)dwCreationDisposition);
            WriteDbgTraceInfoWI("DeviceInfoSet::RegisterDeviceNotificationW", v32);
            WiaTrcLib::Free((WiaTrcLib *)v32, v33);
            dwCreationDispositiona[0] = GetLastError();
            v34 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                             4,
                             0,
                             "Attempt to register for PnP notifications on device (%ws) failed. Error:0x%X",
                             *(_QWORD *)(a2 + 264),
                             *(_QWORD *)dwCreationDispositiona);
          }
          WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"DeviceInfoSet::RegisterDeviceNotificationW", 4, v34);
        }
        else
        {
          LastError = GetLastError();
          v17 = *(_QWORD *)(a2 + 264);
          v18 = LastError;
          v19 = DeviceInfoSet::GetInterfaceName(a1, &v47, a2);
          LODWORD(dwFlagsAndAttributes) = v18;
          v21 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          4,
                          0,
                          "The DeviceInfoSet could not open the interface (%ws) on device (%ws).  Error = 0x%08X",
                          *(_QWORD *)(v19 + 264),
                          v17,
                          dwFlagsAndAttributes);
          v47 = &CSimpleStringBase<unsigned short>::`vftable';
          if ( v49 && v49 != &v48 )
            operator delete(v49, v20);
          v49 = 0;
          v50 = 0;
          WriteDbgTraceInfoWI("DeviceInfoSet::RegisterDeviceNotificationW", v21);
          WiaTrcLib::Free((WiaTrcLib *)v21, v22);
          v23 = GetLastError();
          v24 = *(_QWORD *)(a2 + 264);
          v25 = v23;
          v26 = DeviceInfoSet::GetInterfaceName(a1, &v54, a2);
          LODWORD(dwFlagsAndAttributesa) = v25;
          v27 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           4,
                           0,
                           "The DeviceInfoSet could not open the interface (%ws) on device (%ws).  Error = 0x%08X",
                           *(_QWORD *)(v26 + 264),
                           v24,
                           dwFlagsAndAttributesa);
          WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"DeviceInfoSet::RegisterDeviceNotificationW", 4, v27);
          v54 = &CSimpleStringBase<unsigned short>::`vftable';
          if ( v56 && v56 != &v55 )
            operator delete(v56, v30);
        }
      }
      break;
    }
    v9 = (HANDLE *)*v9;
  }
  if ( v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
}

```

## disassembly

```asm
0x180011f6c  push    rbp
0x180011f6e  push    rbx
0x180011f6f  push    rsi
0x180011f70  push    rdi
0x180011f71  push    r12
0x180011f73  push    r13
0x180011f75  push    r14
0x180011f77  push    r15
0x180011f79  lea     rbp, [rsp-328h]
0x180011f81  sub     rsp, 428h
0x180011f88  mov     rax, cs:__security_cookie
0x180011f8f  xor     rax, rsp
0x180011f92  mov     [rbp+360h+var_50], rax
0x180011f99  mov     r15, rcx
0x180011f9c  mov     r14d, r9d
0x180011f9f  add     rcx, 38h ; '8'; this
0x180011fa3  mov     rdi, r8
0x180011fa6  mov     rsi, rdx
0x180011fa9  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x180011fae  mov     rbx, [r15+20h]
0x180011fb2  mov     r13d, eax
0x180011fb5  test    rbx, rbx
0x180011fb8  jz      loc_1800121AF
0x180011fbe  lea     rcx, [rbx+10h]
0x180011fc2  mov     rdx, rsi
0x180011fc5  call    ??8@YA_NAEBV?$CSimpleStringBase@G@@0@Z; operator==(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180011fca  test    al, al
0x180011fcc  jz      loc_1800122C8
0x180011fd2  mov     rax, [rbx+188h]
0x180011fd9  inc     rax
0x180011fdc  test    rax, 0FFFFFFFFFFFFFFFEh
0x180011fe2  jnz     loc_1800121AF
0x180011fe8  xor     eax, eax
0x180011fea  xorps   xmm0, xmm0
0x180011fed  mov     [rsp+460h+var_3F0], rax
0x180011ff2  mov     rax, [rbx+180h]
0x180011ff9  inc     rax
0x180011ffc  movups  [rsp+460h+NotificationFilter], xmm0
0x180012001  movups  xmmword ptr [rsp+460h+hObject], xmm0
0x180012006  movups  [rsp+460h+var_400], xmm0
0x18001200b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180012011  jnz     short loc_180012087
0x180012013  mov     r8, rsi
0x180012016  lea     rdx, [rbp+360h+var_2B0]
0x18001201d  mov     rcx, r15
0x180012020  call    ?GetInterfaceName@DeviceInfoSet@@QEAA?AV?$CSimpleStringBase@G@@AEBV2@K@Z; DeviceInfoSet::GetInterfaceName(CSimpleStringBase<ushort> const &,ulong)
0x180012025  mov     [rsp+460h+hTemplateFile], 0; hTemplateFile
0x18001202e  xor     r9d, r9d; lpSecurityAttributes
0x180012031  mov     dword ptr [rsp+460h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180012039  xor     r8d, r8d; dwShareMode
0x18001203c  mov     edx, 80000000h; dwDesiredAccess
0x180012041  mov     [rsp+460h+dwCreationDisposition], 3; dwCreationDisposition
0x180012049  mov     rcx, [rax+108h]; lpFileName
0x180012050  call    cs:__imp_CreateFileW
0x180012056  mov     rcx, [rbp+360h+var_1A8]; void *
0x18001205d  mov     [rbx+180h], rax
0x180012064  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18001206b  mov     [rbp+360h+var_2B0], rax
0x180012072  test    rcx, rcx
0x180012075  jz      short loc_180012087
0x180012077  lea     rax, [rbp+360h+var_2A8]
0x18001207e  cmp     rcx, rax
0x180012081  jnz     loc_1800121F2
0x180012087  mov     rcx, [rbx+180h]
0x18001208e  lea     rax, [rcx-1]
0x180012092  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012096  jbe     loc_1800121FC
0x18001209c  call    cs:__imp_GetLastError
0x1800120a2  mov     rbx, [rsi+108h]
0x1800120a9  lea     rdx, [rbp+360h+var_3E0]
0x1800120ad  mov     r8, rsi
0x1800120b0  mov     rcx, r15
0x1800120b3  mov     edi, eax
0x1800120b5  call    ?GetInterfaceName@DeviceInfoSet@@QEAA?AV?$CSimpleStringBase@G@@AEBV2@K@Z; DeviceInfoSet::GetInterfaceName(CSimpleStringBase<ushort> const &,ulong)
0x1800120ba  xor     edx, edx
0x1800120bc  mov     dword ptr [rsp+460h+dwFlagsAndAttributes], edi
0x1800120c0  lea     r8, aTheDeviceinfos; "The DeviceInfoSet could not open the in"...
0x1800120c7  mov     qword ptr [rsp+460h+dwCreationDisposition], rbx
0x1800120cc  mov     r9, [rax+108h]
0x1800120d3  lea     r14d, [rdx+4]
0x1800120d7  mov     ecx, r14d
0x1800120da  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800120df  mov     rcx, [rbp+360h+var_2D8]; void *
0x1800120e6  mov     rbx, rax
0x1800120e9  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800120f0  mov     [rbp+360h+var_3E0], rax
0x1800120f4  test    rcx, rcx
0x1800120f7  jz      short loc_180012106
0x1800120f9  lea     rax, [rbp+360h+var_3D8]
0x1800120fd  cmp     rcx, rax
0x180012100  jnz     loc_1800121E1
0x180012106  mov     rdx, rbx; char *
0x180012109  mov     [rbp+360h+var_2D8], 0
0x180012114  lea     rcx, aDeviceinfosetR_0; "DeviceInfoSet::RegisterDeviceNotificati"...
0x18001211b  mov     [rbp+360h+var_2D0], 0
0x180012126  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001212b  mov     rcx, rbx; this
0x18001212e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180012133  call    cs:__imp_GetLastError
0x180012139  mov     rdi, [rsi+108h]
0x180012140  lea     rdx, [rbp+360h+var_180]
0x180012147  mov     r8, rsi
0x18001214a  mov     rcx, r15
0x18001214d  mov     ebx, eax
0x18001214f  call    ?GetInterfaceName@DeviceInfoSet@@QEAA?AV?$CSimpleStringBase@G@@AEBV2@K@Z; DeviceInfoSet::GetInterfaceName(CSimpleStringBase<ushort> const &,ulong)
0x180012154  mov     dword ptr [rsp+460h+dwFlagsAndAttributes], ebx
0x180012158  lea     r8, aTheDeviceinfos; "The DeviceInfoSet could not open the in"...
0x18001215f  xor     edx, edx
0x180012161  mov     qword ptr [rsp+460h+dwCreationDisposition], rdi
0x180012166  mov     ecx, r14d
0x180012169  mov     r9, [rax+108h]
0x180012170  call    WiaTrace_TraceWithSubCompTraceLevel
0x180012175  mov     r9d, r14d; int
0x180012178  mov     qword ptr [rsp+460h+dwCreationDisposition], rax; lpMem
0x18001217d  lea     r8, aDeviceinfosetR_0; "DeviceInfoSet::RegisterDeviceNotificati"...
0x180012184  call    WiaTrace_ProcessTrace_Ex
0x180012189  mov     rcx, [rbp+360h+var_78]; void *
0x180012190  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180012197  mov     [rbp+360h+var_180], rax
0x18001219e  test    rcx, rcx
0x1800121a1  jz      short loc_1800121AF
0x1800121a3  lea     rax, [rbp+360h+var_178]
0x1800121aa  cmp     rcx, rax
0x1800121ad  jnz     short loc_1800121EB
0x1800121af  test    r13d, r13d
0x1800121b2  jz      short loc_1800121BE
0x1800121b4  lea     rcx, [r15+38h]; lpCriticalSection
0x1800121b8  call    cs:__imp_LeaveCriticalSection
0x1800121be  mov     rcx, [rbp+360h+var_50]
0x1800121c5  xor     rcx, rsp; StackCookie
0x1800121c8  call    __security_check_cookie
0x1800121cd  add     rsp, 428h
0x1800121d4  pop     r15
0x1800121d6  pop     r14
0x1800121d8  pop     r13
0x1800121da  pop     r12
0x1800121dc  pop     rdi
0x1800121dd  pop     rsi
0x1800121de  pop     rbx
0x1800121df  pop     rbp
0x1800121e0  retn
0x1800121e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800121e6  jmp     loc_180012106
0x1800121eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800121f0  jmp     short loc_1800121AF
0x1800121f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800121f7  jmp     loc_180012087
0x1800121fc  mov     [rsp+460h+hObject], rcx
0x180012201  lea     rdx, [rsp+460h+NotificationFilter]; NotificationFilter
0x180012206  mov     rcx, rdi; hRecipient
0x180012209  mov     dword ptr [rsp+460h+NotificationFilter], 38h ; '8'
0x180012211  mov     r8d, r14d; Flags
0x180012214  mov     qword ptr [rsp+460h+NotificationFilter+4], 6
0x18001221d  call    cs:__imp_RegisterDeviceNotificationW
0x180012223  lea     rcx, [rax-1]
0x180012227  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001222b  jbe     loc_1800122D0
0x180012231  call    cs:__imp_GetLastError
0x180012237  mov     rcx, [rsp+460h+hObject]; hObject
0x18001223c  call    cs:__imp_CloseHandle
0x180012242  mov     qword ptr [rbx+180h], 0
0x18001224d  call    cs:__imp_GetLastError
0x180012253  mov     r9, [rsi+108h]
0x18001225a  lea     r8, aAttemptToRegis; "Attempt to register for PnP notificatio"...
0x180012261  xor     edx, edx
0x180012263  mov     [rsp+460h+dwCreationDisposition], eax
0x180012267  lea     r14d, [rdx+4]
0x18001226b  mov     ecx, r14d
0x18001226e  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180012273  mov     rdx, rax; char *
0x180012276  lea     rcx, aDeviceinfosetR_0; "DeviceInfoSet::RegisterDeviceNotificati"...
0x18001227d  mov     rbx, rax
0x180012280  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180012285  mov     rcx, rbx; this
0x180012288  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001228d  call    cs:__imp_GetLastError
0x180012293  mov     r9, [rsi+108h]
0x18001229a  lea     r8, aAttemptToRegis; "Attempt to register for PnP notificatio"...
0x1800122a1  xor     edx, edx
0x1800122a3  mov     [rsp+460h+dwCreationDisposition], eax
0x1800122a7  mov     ecx, r14d
0x1800122aa  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800122af  mov     r9d, r14d; int
0x1800122b2  mov     qword ptr [rsp+460h+dwCreationDisposition], rax; lpMem
0x1800122b7  lea     r8, aDeviceinfosetR_0; "DeviceInfoSet::RegisterDeviceNotificati"...
0x1800122be  call    WiaTrace_ProcessTrace_Ex
0x1800122c3  jmp     loc_1800121AF
0x1800122c8  mov     rbx, [rbx]
0x1800122cb  jmp     loc_180011FB5
0x1800122d0  xor     edx, edx
0x1800122d2  mov     [rbx+188h], rax
0x1800122d9  mov     r9, [rsi+108h]
0x1800122e0  lea     r8, aRegisteredForP; "Registered for PnP notifications on dev"...
0x1800122e7  lea     r14d, [rdx+4]
0x1800122eb  mov     ecx, r14d
0x1800122ee  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800122f3  mov     rdx, rax; char *
0x1800122f6  lea     rcx, aDeviceinfosetR_0; "DeviceInfoSet::RegisterDeviceNotificati"...
0x1800122fd  mov     rbx, rax
0x180012300  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180012305  mov     rcx, rbx; this
0x180012308  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001230d  mov     r9, [rsi+108h]
0x180012314  lea     r8, aRegisteredForP; "Registered for PnP notifications on dev"...
0x18001231b  xor     edx, edx
0x18001231d  mov     ecx, r14d
0x180012320  call    WiaTrace_TraceWithSubCompTraceLevel
0x180012325  jmp     short loc_1800122AF
```
