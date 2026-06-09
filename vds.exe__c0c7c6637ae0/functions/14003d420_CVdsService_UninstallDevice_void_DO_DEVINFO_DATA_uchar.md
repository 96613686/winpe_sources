# CVdsService::UninstallDevice(void *,_DO_DEVINFO_DATA *,uchar *)

- ea: `0x14003d420`
- end: `0x14003d530`
- name: `?UninstallDevice@CVdsService@@AEAAJPEAXPEAU_DO_DEVINFO_DATA@@PEAE@Z`
- size: `272`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, void *, struct _DO_DEVINFO_DATA *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140020590`
- `0x14002afe8`

## callees

- `0x14002e123`
- `0x14003d420`
- `0x140052e80`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x14003d4a5`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x14003d4a5`
- `vdsutil!VdsTraceW` at `0x14003d46c`
- `vdsutil!VdsTraceW` at `0x14003d4c8`
- `vdsutil!VdsTraceW` at `0x14003d4e0`
- `vdsutil!VdsTraceW` at `0x14003d50a`
- `vdsutil!VdsTraceW` at `0x14003d46c`
- `vdsutil!VdsTraceW` at `0x14003d4c8`
- `vdsutil!VdsTraceW` at `0x14003d4e0`
- `vdsutil!VdsTraceW` at `0x14003d50a`

## string_xrefs

- `0x14003d460`: `CVdsService::UninstallDevice`
- `0x14003d501`: `CVdsService::UninstallDevice, hDevInfo=%p, pDevInfoData=%p, pbRebootReq=%p`
- `0x14003d4be`: `CVdsService::UninstallDevice, query removal was vetoed by %ws (veto type %u)`
- `0x14003d4d4`: `EXIT CVdsService::UninstallDevice, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::UninstallDevice(
        CVdsService *this,
        char *a2,
        struct _DO_DEVINFO_DATA *a3,
        unsigned __int8 *a4)
{
  unsigned int v7; // ebx
  CONFIGRET v8; // eax
  _PNP_VETO_TYPE pVetoType[4]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR pszVetoName[264]; // [rsp+40h] [rbp-238h] BYREF

  pVetoType[0] = PNP_VetoTypeUnknown;
  memset_0(pszVetoName, 0, 0x208u);
  VdsTraceW(2, L"CVdsService::UninstallDevice");
  if ( (unsigned __int64)(a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a3 && a4 )
  {
    v7 = 0;
    *a4 = 0;
    v8 = CM_Query_And_Remove_SubTreeW(*((_DWORD *)a3 + 5), pVetoType, pszVetoName, 0x104u, 3u);
    if ( v8 )
    {
      if ( v8 == 23 )
      {
        VdsTraceW(
          1,
          L"CVdsService::UninstallDevice, query removal was vetoed by %ws (veto type %u)",
          pszVetoName,
          (unsigned int)pVetoType[0]);
      }
      else if ( v8 == 5 )
      {
        v7 = -2147024883;
        goto LABEL_8;
      }
      *a4 = 1;
    }
LABEL_8:
    VdsTraceW(2, L"EXIT CVdsService::UninstallDevice, hr=%lX", v7);
    return v7;
  }
  VdsTraceW(0, L"CVdsService::UninstallDevice, hDevInfo=%p, pDevInfoData=%p, pbRebootReq=%p", a2, a3, a4);
  return 2147942487LL;
}

```

## disassembly

```asm
0x14003d420  push    rbx
0x14003d422  push    rsi
0x14003d423  push    rdi
0x14003d424  sub     rsp, 260h
0x14003d42b  mov     rax, cs:__security_cookie
0x14003d432  xor     rax, rsp
0x14003d435  mov     [rsp+278h+var_28], rax
0x14003d43d  mov     rsi, r8
0x14003d440  mov     [rsp+278h+pVetoType], 0
0x14003d448  mov     rbx, rdx
0x14003d44b  lea     rcx, [rsp+278h+pszVetoName]; void *
0x14003d450  xor     edx, edx; Val
0x14003d452  mov     r8d, 208h; Size
0x14003d458  mov     rdi, r9
0x14003d45b  call    memset_0
0x14003d460  lea     rdx, aCvdsserviceUni_35; "CVdsService::UninstallDevice"
0x14003d467  mov     ecx, 2
0x14003d46c  call    cs:__imp_VdsTraceW
0x14003d472  lea     rax, [rbx-1]
0x14003d476  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003d47a  ja      short loc_14003D4F6
0x14003d47c  test    rsi, rsi
0x14003d47f  jz      short loc_14003D4F6
0x14003d481  test    rdi, rdi
0x14003d484  jz      short loc_14003D4F6
0x14003d486  xor     ebx, ebx
0x14003d488  mov     [rsp+278h+ulFlags], 3; ulFlags
0x14003d490  mov     [rdi], bl
0x14003d492  lea     r8, [rsp+278h+pszVetoName]; pszVetoName
0x14003d497  mov     ecx, [rsi+14h]; dnAncestor
0x14003d49a  lea     rdx, [rsp+278h+pVetoType]; pVetoType
0x14003d49f  mov     r9d, 104h; ulNameLength
0x14003d4a5  call    cs:__imp_CM_Query_And_Remove_SubTreeW
0x14003d4ab  test    eax, eax
0x14003d4ad  jz      short loc_14003D4D1
0x14003d4af  cmp     eax, 17h
0x14003d4b2  jnz     short loc_14003D4EA
0x14003d4b4  mov     r9d, [rsp+278h+pVetoType]
0x14003d4b9  lea     r8, [rsp+278h+pszVetoName]
0x14003d4be  lea     rdx, aCvdsserviceUni_24; "CVdsService::UninstallDevice, query rem"...
0x14003d4c5  lea     ecx, [rbx+1]
0x14003d4c8  call    cs:__imp_VdsTraceW
0x14003d4ce  mov     byte ptr [rdi], 1
0x14003d4d1  mov     r8d, ebx
0x14003d4d4  lea     rdx, aExitCvdsservic_11; "EXIT CVdsService::UninstallDevice, hr=%"...
0x14003d4db  mov     ecx, 2
0x14003d4e0  call    cs:__imp_VdsTraceW
0x14003d4e6  mov     eax, ebx
0x14003d4e8  jmp     short loc_14003D515
0x14003d4ea  cmp     eax, 5
0x14003d4ed  jnz     short loc_14003D4CE
0x14003d4ef  mov     ebx, 8007000Dh
0x14003d4f4  jmp     short loc_14003D4D1
0x14003d4f6  mov     r9, rsi
0x14003d4f9  mov     qword ptr [rsp+278h+ulFlags], rdi
0x14003d4fe  mov     r8, rbx
0x14003d501  lea     rdx, aCvdsserviceUni_18; "CVdsService::UninstallDevice, hDevInfo="...
0x14003d508  xor     ecx, ecx
0x14003d50a  call    cs:__imp_VdsTraceW
0x14003d510  mov     eax, 80070057h
0x14003d515  mov     rcx, [rsp+278h+var_28]
0x14003d51d  xor     rcx, rsp; StackCookie
0x14003d520  call    __security_check_cookie
0x14003d525  add     rsp, 260h
0x14003d52c  pop     rdi
0x14003d52d  pop     rsi
0x14003d52e  pop     rbx
0x14003d52f  retn
```
