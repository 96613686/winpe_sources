# CMountPoint::_EnumVolumes(IHardwareDevices *)

- ea: `0x1801304d4`
- end: `0x18013066f`
- name: `?_EnumVolumes@CMountPoint@@CAJPEAUIHardwareDevices@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct IHardwareDevices *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x1802cf274`

## callees

- `0x1801304d4`
- `0x180131ac0`
- `0x180132b70`
- `0x1801348fc`
- `0x180159314`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130606`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801305f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180130606`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMountPoint::_EnumVolumes(struct IHardwareDevices *a1)
{
  int v1; // ebx
  CVolume *v3; // [rsp+20h] [rbp-69h] BYREF
  _BYTE v4[80]; // [rsp+30h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-9h]
  LPVOID v6; // [rsp+88h] [rbp-1h]
  LPVOID v7; // [rsp+90h] [rbp+7h]
  LPVOID v8; // [rsp+98h] [rbp+Fh]
  LPVOID v9; // [rsp+A0h] [rbp+17h]
  LPVOID v10; // [rsp+A8h] [rbp+1Fh]
  LPVOID v11; // [rsp+B0h] [rbp+27h]
  LPVOID v12; // [rsp+B8h] [rbp+2Fh]
  LPVOID v13; // [rsp+C0h] [rbp+37h]
  LPVOID v14; // [rsp+C8h] [rbp+3Fh]
  __int64 v15; // [rsp+D0h] [rbp+47h] BYREF

  if ( g_esServerMode == 3 )
  {
    v15 = 0;
    v1 = (*(__int64 (__fastcall **)(struct IHardwareDevices *, __int64, __int64 *))(*(_QWORD *)a1 + 24LL))(a1, 1, &v15);
    if ( v1 >= 0 )
    {
      memset_0(v4, 0, 0xA0u);
      while ( !(*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 24LL))(v15, v4) )
      {
        v3 = 0;
        if ( (int)CMtPtLocal::_CreateVolume((const struct tagVOLUMEINFO *)v4, &v3) >= 0 )
        {
          CMtPtLocal::_UpdateVolumeRegInfo((const struct tagVOLUMEINFO *)v4);
          CVolume::Release(v3);
        }
        CoTaskMemFree(pv);
        CoTaskMemFree(v6);
        CoTaskMemFree(v7);
        CoTaskMemFree(v8);
        CoTaskMemFree(v9);
        CoTaskMemFree(v10);
        CoTaskMemFree(v11);
        CoTaskMemFree(v12);
        CoTaskMemFree(v13);
        CoTaskMemFree(v14);
      }
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  else
  {
    return (unsigned int)CMountPoint::_EnumVolumesNonPrimaryProcess(0);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801304d4  mov     [rsp-8+arg_8], rbx
0x1801304d9  push    rbp
0x1801304da  lea     rbp, [rsp-57h]
0x1801304df  sub     rsp, 0E0h
0x1801304e6  mov     rax, cs:__security_cookie
0x1801304ed  xor     rax, rsp
0x1801304f0  mov     [rbp+57h+var_8], rax
0x1801304f4  cmp     cs:?g_esServerMode@@3W4EXPLORERSERVER@@A, 3; EXPLORERSERVER g_esServerMode
0x1801304fb  jnz     loc_180130664
0x180130501  mov     [rbp+57h+var_10], 0
0x180130509  mov     rax, [rcx]
0x18013050c  lea     r8, [rbp+57h+var_10]
0x180130510  mov     edx, 1
0x180130515  mov     rax, [rax+18h]
0x180130519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013051e  mov     ebx, eax
0x180130520  test    eax, eax
0x180130522  js      loc_180130617
0x180130528  xor     edx, edx; Val
0x18013052a  mov     r8d, 0A0h; Size
0x180130530  lea     rcx, [rbp+57h+var_B0]; void *
0x180130534  call    memset_0
0x180130539  mov     rcx, [rbp+57h+var_10]
0x18013053d  mov     rdx, [rcx]
0x180130540  mov     rax, [rdx+18h]
0x180130544  lea     rdx, [rbp+57h+var_B0]
0x180130548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013054d  test    eax, eax
0x18013054f  jnz     loc_180130617
0x180130555  mov     [rbp+57h+var_C0], 0
0x18013055d  lea     rdx, [rbp+57h+var_C0]; struct CVolume **
0x180130561  lea     rcx, [rbp+57h+var_B0]; struct tagVOLUMEINFO *
0x180130565  call    ?_CreateVolume@CMtPtLocal@@CAJPEBUtagVOLUMEINFO@@PEAPEAVCVolume@@@Z; CMtPtLocal::_CreateVolume(tagVOLUMEINFO const *,CVolume * *)
0x18013056a  test    eax, eax
0x18013056c  jns     loc_18013064D
0x180130572  mov     rcx, [rbp+57h+pv]; pv
0x180130576  call    cs:__imp_CoTaskMemFree
0x18013057d  nop     dword ptr [rax+rax+00h]
0x180130582  mov     rcx, [rbp+57h+var_58]; pv
0x180130586  call    cs:__imp_CoTaskMemFree
0x18013058d  nop     dword ptr [rax+rax+00h]
0x180130592  mov     rcx, [rbp+57h+var_50]; pv
0x180130596  call    cs:__imp_CoTaskMemFree
0x18013059d  nop     dword ptr [rax+rax+00h]
0x1801305a2  mov     rcx, [rbp+57h+var_48]; pv
0x1801305a6  call    cs:__imp_CoTaskMemFree
0x1801305ad  nop     dword ptr [rax+rax+00h]
0x1801305b2  mov     rcx, [rbp+57h+var_40]; pv
0x1801305b6  call    cs:__imp_CoTaskMemFree
0x1801305bd  nop     dword ptr [rax+rax+00h]
0x1801305c2  mov     rcx, [rbp+57h+var_38]; pv
0x1801305c6  call    cs:__imp_CoTaskMemFree
0x1801305cd  nop     dword ptr [rax+rax+00h]
0x1801305d2  mov     rcx, [rbp+57h+var_30]; pv
0x1801305d6  call    cs:__imp_CoTaskMemFree
0x1801305dd  nop     dword ptr [rax+rax+00h]
0x1801305e2  mov     rcx, [rbp+57h+var_28]; pv
0x1801305e6  call    cs:__imp_CoTaskMemFree
0x1801305ed  nop     dword ptr [rax+rax+00h]
0x1801305f2  mov     rcx, [rbp+57h+var_20]; pv
0x1801305f6  call    cs:__imp_CoTaskMemFree
0x1801305fd  nop     dword ptr [rax+rax+00h]
0x180130602  mov     rcx, [rbp+57h+var_18]; pv
0x180130606  call    cs:__imp_CoTaskMemFree
0x18013060d  nop     dword ptr [rax+rax+00h]
0x180130612  jmp     loc_180130539
0x180130617  mov     rcx, [rbp+57h+var_10]
0x18013061b  test    rcx, rcx
0x18013061e  jz      short loc_18013062D
0x180130620  mov     rax, [rcx]
0x180130623  mov     rax, [rax+10h]
0x180130627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013062c  nop
0x18013062d  mov     eax, ebx
0x18013062f  mov     rcx, [rbp+57h+var_8]
0x180130633  xor     rcx, rsp; StackCookie
0x180130636  call    __security_check_cookie
0x18013063b  mov     rbx, [rsp+0E0h+arg_8]
0x180130643  add     rsp, 0E0h
0x18013064a  pop     rbp
0x18013064b  retn
0x18013064d  lea     rcx, [rbp+57h+var_B0]; struct tagVOLUMEINFO *
0x180130651  call    ?_UpdateVolumeRegInfo@CMtPtLocal@@CAJPEBUtagVOLUMEINFO@@@Z; CMtPtLocal::_UpdateVolumeRegInfo(tagVOLUMEINFO const *)
0x180130656  mov     rcx, [rbp+57h+var_C0]; this
0x18013065a  call    ?Release@CVolume@@QEAAKXZ; CVolume::Release(void)
0x18013065f  jmp     loc_180130572
0x180130664  xor     ecx, ecx; lpCriticalSection
0x180130666  call    ?_EnumVolumesNonPrimaryProcess@CMountPoint@@CAJPEAVCCritSecDelayInitBase@@@Z; CMountPoint::_EnumVolumesNonPrimaryProcess(CCritSecDelayInitBase *)
0x18013066b  mov     ebx, eax
0x18013066d  jmp     short loc_18013062D
```
