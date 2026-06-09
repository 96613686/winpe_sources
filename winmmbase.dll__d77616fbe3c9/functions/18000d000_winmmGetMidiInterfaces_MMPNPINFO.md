# winmmGetMidiInterfaces(_MMPNPINFO *)

- ea: `0x18000d000`
- end: `0x18000d38d`
- name: `?winmmGetMidiInterfaces@@YAXPEAU_MMPNPINFO@@@Z`
- size: `909`
- prototype: `void __fastcall(struct _MMPNPINFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c784`

## callees

- `0x18000d000`
- `0x18000db00`
- `0x18000df08`
- `0x18000eb68`
- `0x1800106c0`
- `0x18001c058`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d307`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d142`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d32d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d142`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d32d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x18000d2ae`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x18000d2ae`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000d24e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000d24e`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000d28d`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000d28d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000d2fd`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000d2fd`
- `MMDevAPI!__imp_MMDeviceGetDeviceEnumerator` at `0x18000d03e`
- `MMDevAPI!__imp_MMDeviceGetDeviceEnumerator` at `0x18000d03e`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall winmmGetMidiInterfaces(struct _MMPNPINFO *a1)
{
  unsigned int i; // ebx
  __int64 DeviceInfoList; // rsi
  PROPVARIANT v4; // rdi
  unsigned int v5; // [rsp+30h] [rbp-89h] BYREF
  struct IUnknown *v6; // [rsp+38h] [rbp-81h] BYREF
  ULONG pulStatus; // [rsp+40h] [rbp-79h] BYREF
  __int64 v8; // [rsp+48h] [rbp-71h] BYREF
  struct IUnknown *v9; // [rsp+50h] [rbp-69h] BYREF
  __int64 v10; // [rsp+58h] [rbp-61h] BYREF
  ULONG pulProblemNumber; // [rsp+60h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-51h] BYREF
  LPVOID v13; // [rsp+70h] [rbp-49h] BYREF
  __int64 v14; // [rsp+78h] [rbp-41h] BYREF
  __int64 v15; // [rsp+80h] [rbp-39h] BYREF
  __int64 v16; // [rsp+88h] [rbp-31h] BYREF
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v18; // [rsp+A0h] [rbp-19h]
  __int128 v19; // [rsp+A8h] [rbp-11h] BYREF
  DEVINST dnDevInst[4]; // [rsp+B8h] [rbp-1h]
  __int128 v21; // [rsp+C8h] [rbp+Fh]

  v16 = 0;
  v15 = 0;
  v10 = 0;
  v5 = 0;
  if ( (int)MMDeviceGetDeviceEnumerator(&v15) >= 0
    && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v15)(v15, &GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0, &v16) >= 0
    && (*(int (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v16 + 72LL))(
         v16,
         0xFFFFFFFFLL,
         &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196,
         &v10) >= 0
    && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, &v5) >= 0 )
  {
    for ( i = 0; i < v5; ++i )
    {
      v6 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v10 + 32LL))(v10, i, &v6) >= 0 )
      {
        v9 = 0;
        v8 = 0;
        if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, __int64 *))v6->lpVtbl[1].AddRef)(v6, 0, &v8) >= 0 )
        {
          *(_OWORD *)pvar = 0;
          v18 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v8 + 40LL))(
                 v8,
                 PKEY_MMDEVAPI_MidiCapable,
                 pvar) >= 0
            && LOWORD(pvar[0]) == 19
            && LODWORD(pvar[1]) )
          {
            v4 = 0;
            PropVariantClear(pvar);
            if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v8 + 40LL))(
                   v8,
                   PKEY_MMDEVAPI_ActiveTime,
                   pvar) >= 0
              && LOWORD(pvar[0]) == 21 )
            {
              v4 = pvar[1];
            }
            if ( !(unsigned __int8)ATL::CComPtrBase<IPnpInterface>::IsEqualObject(&v9, v6) )
              ATL::AtlComQIPtrAssign(&v9, v6, &GUID_3ade56af_4375_4413_9c91_4c652595ab07);
            if ( v9 )
            {
              v14 = 0;
              if ( ((int (__fastcall *)(struct IUnknown *, __int64 *))v9->lpVtbl[1].QueryInterface)(v9, &v14) >= 0 )
              {
                v13 = 0;
                if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 32LL))(v14, &v13) >= 0 )
                {
                  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
                  if ( DeviceInfoList != -1 )
                  {
                    v19 = 0;
                    *(_OWORD *)dnDevInst = 0;
                    v21 = 0;
                    LODWORD(v19) = 48;
                    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, v13, 0, 0, &v19) )
                    {
                      pulStatus = 0;
                      pulProblemNumber = 0;
                      if ( !CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst[1], 0)
                        && (pulStatus & 8) != 0 )
                      {
                        pv = 0;
                        if ( ((int (__fastcall *)(struct IUnknown *, LPVOID *))v6->lpVtbl[1].Release)(v6, &pv) >= 0 )
                        {
                          InstallDeviceEndpoints(a1, (const unsigned __int16 *)pv, (unsigned __int64)v4, 8u);
                          CoTaskMemFree(pv);
                        }
                      }
                    }
                    DevObjDestroyDeviceInfoList(DeviceInfoList);
                  }
                  CoTaskMemFree(v13);
                }
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
            }
          }
          PropVariantClear(pvar);
        }
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        if ( v9 )
          ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
      }
      if ( v6 )
        ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
}

```

## disassembly

```asm
0x18000d000  push    rbp
0x18000d002  push    rbx
0x18000d003  push    rsi
0x18000d004  push    rdi
0x18000d005  push    r14
0x18000d007  push    r15
0x18000d009  lea     rbp, [rsp-2Fh]
0x18000d00e  sub     rsp, 0E8h
0x18000d015  mov     rax, cs:__security_cookie
0x18000d01c  xor     rax, rsp
0x18000d01f  mov     [rbp+57h+var_38], rax
0x18000d023  mov     r14, rcx
0x18000d026  xor     r15d, r15d
0x18000d029  mov     [rbp+57h+var_88], r15
0x18000d02d  mov     [rbp+57h+var_90], r15
0x18000d031  mov     [rbp+57h+var_B8], r15
0x18000d035  mov     [rsp+110h+var_E0], r15d
0x18000d03a  lea     rcx, [rbp+57h+var_90]
0x18000d03e  call    cs:__imp_MMDeviceGetDeviceEnumerator
0x18000d044  test    eax, eax
0x18000d046  js      loc_18000D198
0x18000d04c  mov     rcx, [rbp+57h+var_90]
0x18000d050  mov     rax, [rcx]
0x18000d053  lea     r8, [rbp+57h+var_88]
0x18000d057  lea     rdx, _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0
0x18000d05e  mov     rax, [rax]
0x18000d061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d066  test    eax, eax
0x18000d068  js      loc_18000D198
0x18000d06e  mov     rcx, [rbp+57h+var_88]
0x18000d072  mov     rax, [rcx]
0x18000d075  lea     r9, [rbp+57h+var_B8]
0x18000d079  lea     r8, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x18000d080  mov     edx, 0FFFFFFFFh
0x18000d085  mov     rax, [rax+48h]
0x18000d089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d08e  test    eax, eax
0x18000d090  js      loc_18000D198
0x18000d096  mov     rcx, [rbp+57h+var_B8]
0x18000d09a  mov     rax, [rcx]
0x18000d09d  lea     rdx, [rsp+110h+var_E0]
0x18000d0a2  mov     rax, [rax+18h]
0x18000d0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ab  test    eax, eax
0x18000d0ad  js      loc_18000D198
0x18000d0b3  mov     ebx, r15d
0x18000d0b6  cmp     [rsp+110h+var_E0], ebx
0x18000d0ba  jbe     loc_18000D198
0x18000d0c0  mov     [rsp+110h+var_D8], r15
0x18000d0c5  mov     rcx, [rbp+57h+var_B8]
0x18000d0c9  mov     rax, [rcx]
0x18000d0cc  lea     r8, [rsp+110h+var_D8]
0x18000d0d1  mov     edx, ebx
0x18000d0d3  mov     rax, [rax+20h]
0x18000d0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0dc  test    eax, eax
0x18000d0de  js      loc_18000D175
0x18000d0e4  mov     [rbp+57h+var_C0], r15
0x18000d0e8  mov     [rbp+57h+var_C8], r15
0x18000d0ec  mov     rcx, [rsp+110h+var_D8]
0x18000d0f1  mov     rax, [rcx]
0x18000d0f4  lea     r8, [rbp+57h+var_C8]
0x18000d0f8  xor     edx, edx
0x18000d0fa  mov     rax, [rax+20h]
0x18000d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d103  test    eax, eax
0x18000d105  js      short loc_18000D149
0x18000d107  xorps   xmm0, xmm0
0x18000d10a  xor     eax, eax
0x18000d10c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000d110  mov     [rbp+57h+var_70], rax
0x18000d114  mov     rcx, [rbp+57h+var_C8]
0x18000d118  mov     rax, [rcx]
0x18000d11b  lea     r8, [rbp+57h+pvar]
0x18000d11f  lea     rdx, PKEY_MMDEVAPI_MidiCapable
0x18000d126  mov     rax, [rax+28h]
0x18000d12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d12f  test    eax, eax
0x18000d131  js      short loc_18000D13E
0x18000d133  cmp     word ptr [rbp+57h+pvar], 13h
0x18000d138  jz      loc_18000D31C
0x18000d13e  lea     rcx, [rbp+57h+pvar]; pvar
0x18000d142  call    cs:__imp_PropVariantClear
0x18000d148  nop
0x18000d149  mov     rcx, [rbp+57h+var_C8]
0x18000d14d  test    rcx, rcx
0x18000d150  jz      short loc_18000D15F
0x18000d152  mov     rax, [rcx]
0x18000d155  mov     rax, [rax+10h]
0x18000d159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d15e  nop
0x18000d15f  mov     rcx, [rbp+57h+var_C0]
0x18000d163  test    rcx, rcx
0x18000d166  jz      short loc_18000D175
0x18000d168  mov     rax, [rcx]
0x18000d16b  mov     rax, [rax+10h]
0x18000d16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d174  nop
0x18000d175  mov     rcx, [rsp+110h+var_D8]
0x18000d17a  test    rcx, rcx
0x18000d17d  jz      short loc_18000D18C
0x18000d17f  mov     rax, [rcx]
0x18000d182  mov     rax, [rax+10h]
0x18000d186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d18b  nop
0x18000d18c  inc     ebx
0x18000d18e  cmp     ebx, [rsp+110h+var_E0]
0x18000d192  jb      loc_18000D0C0
0x18000d198  mov     rcx, [rbp+57h+var_B8]
0x18000d19c  test    rcx, rcx
0x18000d19f  jz      short loc_18000D1AE
0x18000d1a1  mov     rax, [rcx]
0x18000d1a4  mov     rax, [rax+10h]
0x18000d1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ad  nop
0x18000d1ae  mov     rcx, [rbp+57h+var_90]
0x18000d1b2  test    rcx, rcx
0x18000d1b5  jz      short loc_18000D1C4
0x18000d1b7  mov     rax, [rcx]
0x18000d1ba  mov     rax, [rax+10h]
0x18000d1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1c3  nop
0x18000d1c4  mov     rcx, [rbp+57h+var_88]
0x18000d1c8  test    rcx, rcx
0x18000d1cb  jz      short loc_18000D1DA
0x18000d1cd  mov     rax, [rcx]
0x18000d1d0  mov     rax, [rax+10h]
0x18000d1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d9  nop
0x18000d1da  mov     rcx, [rbp+57h+var_38]
0x18000d1de  xor     rcx, rsp; StackCookie
0x18000d1e1  call    __security_check_cookie
0x18000d1e6  add     rsp, 0E8h
0x18000d1ed  pop     r15
0x18000d1ef  pop     r14
0x18000d1f1  pop     rdi
0x18000d1f2  pop     rsi
0x18000d1f3  pop     rbx
0x18000d1f4  pop     rbp
0x18000d1f5  retn
0x18000d1f6  mov     rcx, [rbp+57h+var_C0]
0x18000d1fa  test    rcx, rcx
0x18000d1fd  jz      loc_18000D13E
0x18000d203  mov     [rbp+57h+var_98], r15
0x18000d207  mov     rax, [rcx]
0x18000d20a  lea     rdx, [rbp+57h+var_98]
0x18000d20e  mov     rax, [rax+18h]
0x18000d212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d217  test    eax, eax
0x18000d219  js      loc_18000D30E
0x18000d21f  mov     [rbp+57h+var_A0], r15
0x18000d223  mov     rcx, [rbp+57h+var_98]
0x18000d227  mov     rax, [rcx]
0x18000d22a  lea     rdx, [rbp+57h+var_A0]
0x18000d22e  mov     rax, [rax+20h]
0x18000d232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d237  test    eax, eax
0x18000d239  js      loc_18000D30E
0x18000d23f  mov     [rsp+110h+var_F0], r15
0x18000d244  xor     r9d, r9d
0x18000d247  xor     r8d, r8d
0x18000d24a  xor     edx, edx
0x18000d24c  xor     ecx, ecx
0x18000d24e  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000d254  mov     rsi, rax
0x18000d257  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d25b  jz      loc_18000D303
0x18000d261  xorps   xmm0, xmm0
0x18000d264  movups  [rbp+57h+var_68], xmm0
0x18000d268  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x18000d26c  movups  [rbp+57h+var_48], xmm0
0x18000d270  mov     dword ptr [rbp+57h+var_68], 30h ; '0'
0x18000d277  lea     rax, [rbp+57h+var_68]
0x18000d27b  mov     [rsp+110h+var_F0], rax
0x18000d280  xor     r9d, r9d
0x18000d283  xor     r8d, r8d
0x18000d286  mov     rdx, [rbp+57h+var_A0]
0x18000d28a  mov     rcx, rsi
0x18000d28d  call    cs:__imp_DevObjOpenDeviceInfo
0x18000d293  test    eax, eax
0x18000d295  jz      short loc_18000D2FA
0x18000d297  mov     [rbp+57h+pulStatus], r15d
0x18000d29b  mov     [rbp+57h+pulProblemNumber], r15d
0x18000d29f  xor     r9d, r9d; ulFlags
0x18000d2a2  mov     r8d, [rbp+57h+dnDevInst+4]; dnDevInst
0x18000d2a6  lea     rdx, [rbp+57h+pulProblemNumber]; pulProblemNumber
0x18000d2aa  lea     rcx, [rbp+57h+pulStatus]; pulStatus
0x18000d2ae  call    cs:__imp_CM_Get_DevNode_Status
0x18000d2b4  test    eax, eax
0x18000d2b6  jnz     short loc_18000D2FA
0x18000d2b8  test    byte ptr [rbp+57h+pulStatus], 8
0x18000d2bc  jz      short loc_18000D2FA
0x18000d2be  mov     [rbp+57h+pv], r15
0x18000d2c2  mov     rcx, [rsp+110h+var_D8]
0x18000d2c7  mov     rax, [rcx]
0x18000d2ca  lea     rdx, [rbp+57h+pv]
0x18000d2ce  mov     rax, [rax+28h]
0x18000d2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2d7  test    eax, eax
0x18000d2d9  js      short loc_18000D2FA
0x18000d2db  mov     r9d, 8; unsigned int
0x18000d2e1  mov     r8, rdi; unsigned __int64
0x18000d2e4  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18000d2e8  mov     rcx, r14; struct _MMPNPINFO *
0x18000d2eb  call    ?InstallDeviceEndpoints@@YAPEAU_MMDEVICEINTERFACEINFO@@PEAU_MMPNPINFO@@PEBG_KK@Z; InstallDeviceEndpoints(_MMPNPINFO *,ushort const *,unsigned __int64,ulong)
0x18000d2f0  mov     rcx, [rbp+57h+pv]; pv
0x18000d2f4  call    cs:__imp_CoTaskMemFree
0x18000d2fa  mov     rcx, rsi
0x18000d2fd  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000d303  mov     rcx, [rbp+57h+var_A0]; pv
0x18000d307  call    cs:__imp_CoTaskMemFree
0x18000d30d  nop
0x18000d30e  lea     rcx, [rbp+57h+var_98]
0x18000d312  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d317  jmp     loc_18000D13E
0x18000d31c  cmp     dword ptr [rbp+57h+pvar+8], 0
0x18000d320  jz      loc_18000D13E
0x18000d326  mov     rdi, r15
0x18000d329  lea     rcx, [rbp+57h+pvar]; pvar
0x18000d32d  call    cs:__imp_PropVariantClear
0x18000d333  mov     rcx, [rbp+57h+var_C8]
0x18000d337  mov     rax, [rcx]
0x18000d33a  lea     r8, [rbp+57h+pvar]
0x18000d33e  lea     rdx, PKEY_MMDEVAPI_ActiveTime
0x18000d345  mov     rax, [rax+28h]
0x18000d349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34e  test    eax, eax
0x18000d350  js      short loc_18000D35C
0x18000d352  cmp     word ptr [rbp+57h+pvar], 15h
0x18000d357  cmovz   rdi, [rbp+57h+pvar+8]
0x18000d35c  mov     rdx, [rsp+110h+var_D8]
0x18000d361  lea     rcx, [rbp+57h+var_C0]
0x18000d365  call    ?IsEqualObject@?$CComPtrBase@UIPnpInterface@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<IPnpInterface>::IsEqualObject(IUnknown *)
0x18000d36a  test    al, al
0x18000d36c  jnz     loc_18000D1F6
0x18000d372  lea     r8, _GUID_3ade56af_4375_4413_9c91_4c652595ab07; struct _GUID *
0x18000d379  mov     rdx, [rsp+110h+var_D8]; struct IUnknown *
0x18000d37e  lea     rcx, [rbp+57h+var_C0]; struct IUnknown **
0x18000d382  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18000d387  jmp     loc_18000D1F6
```
