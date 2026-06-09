# WaitForInterface

- ea: `0x180006c60`
- end: `0x180006e7f`
- name: `WaitForInterface`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006290`

## callees

- `0x180006c60`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006d69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006d69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006e03`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e4f`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180006e3b`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180006e3b`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180006de9`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180006de9`

## pseudocode

```c
__int64 __fastcall WaitForInterface(__int64 a1)
{
  __int64 v1; // rax
  HANDLE EventW; // rax
  void *v4; // rdi
  signed int LastError; // eax
  signed int v6; // ebx
  DWORD v7; // eax
  __int64 v9; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v10; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h] BYREF
  DEVPROPKEY v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+8Ch] [rbp-74h]
  __int64 v14; // [rsp+90h] [rbp-70h]
  int v15; // [rsp+98h] [rbp-68h]
  int v16; // [rsp+9Ch] [rbp-64h]
  __int64 v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A8h] [rbp-58h]
  int v19; // [rsp+ACh] [rbp-54h]
  DEVPROPKEY v20; // [rsp+B0h] [rbp-50h]
  int v21; // [rsp+C4h] [rbp-3Ch]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  int v23; // [rsp+D0h] [rbp-30h]
  int v24; // [rsp+D4h] [rbp-2Ch]
  char *v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E4h] [rbp-1Ch]
  DEVPROPKEY v28; // [rsp+E8h] [rbp-18h]
  int v29; // [rsp+FCh] [rbp-4h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  int v31; // [rsp+108h] [rbp+8h]
  int v32; // [rsp+10Ch] [rbp+Ch]
  GUID *v33; // [rsp+110h] [rbp+10h]

  v11 = 131074;
  v9 = 0;
  v19 = 0;
  v27 = 0;
  v10 = 0;
  v12 = DEVPKEY_Device_InstanceId;
  v1 = -1;
  v13 = 0;
  v14 = 0;
  v15 = 18;
  while ( *(_WORD *)(a1 + 2 * v1++ + 2) != 0 )
    ;
  v17 = a1;
  v16 = 2 * v1 + 2;
  v20 = DEVPKEY_DeviceInterface_Enabled;
  v25 = s_fDevpropTrue;
  v28 = DEVPKEY_DeviceInterface_ClassGuid;
  v33 = &GUID_DEVINTERFACE_NET;
  v18 = 2;
  v21 = 0;
  v22 = 0;
  v23 = 17;
  v24 = 1;
  v26 = 2;
  v29 = 0;
  v30 = 0;
  v31 = 13;
  v32 = 16;
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = EventW;
  if ( !EventW )
    goto LABEL_4;
  *(_QWORD *)&v10 = EventW;
  DWORD2(v10) = 0;
  v6 = DevCreateObjectQuery(1, 1, 0, 0, 3, &v11, DevQueryCallback, &v10, &v9);
  if ( v6 < 0 )
    goto LABEL_12;
  v7 = WaitForSingleObject(v4, 0x7530u);
  if ( !v7 )
  {
    v6 = DWORD2(v10);
    goto LABEL_12;
  }
  if ( v7 == -1 )
  {
LABEL_4:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = -2147418113;
    if ( v7 == 258 )
      v6 = DWORD2(v10);
  }
LABEL_12:
  if ( v9 )
    DevCloseObjectQuery();
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006c60  mov     [rsp-8+arg_0], rbx
0x180006c65  mov     [rsp-8+arg_8], rdi
0x180006c6a  push    rbp
0x180006c6b  lea     rbp, [rsp-30h]
0x180006c70  sub     rsp, 130h
0x180006c77  mov     rax, cs:__security_cookie
0x180006c7e  xor     rax, rsp
0x180006c81  mov     [rbp+30h+var_10], rax
0x180006c85  xor     ebx, ebx
0x180006c87  mov     [rsp+130h+var_C0], 20002h
0x180006c90  xor     eax, eax
0x180006c92  mov     [rsp+130h+var_E0], rbx
0x180006c97  xorps   xmm0, xmm0
0x180006c9a  mov     [rbp+30h+var_84], eax
0x180006c9d  mov     [rbp+30h+var_4C], eax
0x180006ca0  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180006ca6  movups  [rsp+130h+var_D8], xmm0
0x180006cab  mov     [rbp+30h+var_A8], eax
0x180006cae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006cb5  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180006cbc  mov     [rbp+30h+var_A4], ebx
0x180006cbf  mov     [rbp+30h+var_A0], rbx
0x180006cc3  movups  [rsp+130h+var_B8], xmm0
0x180006cc8  mov     [rbp+30h+var_98], 12h
0x180006ccf  nop
0x180006cd0  cmp     [rcx+rax*2+2], bx
0x180006cd5  lea     rax, [rax+1]
0x180006cd9  jnz     short loc_180006CD0
0x180006cdb  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x180006ce2  lea     eax, ds:2[rax*2]
0x180006ce9  mov     [rbp+30h+var_90], rcx
0x180006ced  mov     [rbp+30h+var_94], eax
0x180006cf0  xor     r9d, r9d; lpName
0x180006cf3  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180006cf9  xor     r8d, r8d; bInitialState
0x180006cfc  mov     [rbp+30h+var_70], eax
0x180006cff  xor     edx, edx; bManualReset
0x180006d01  lea     rax, s_fDevpropTrue
0x180006d08  movaps  [rbp+30h+var_80], xmm0
0x180006d0c  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180006d13  mov     [rbp+30h+var_58], rax
0x180006d17  xor     ecx, ecx; lpEventAttributes
0x180006d19  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180006d1f  mov     [rbp+30h+var_38], eax
0x180006d22  lea     rax, GUID_DEVINTERFACE_NET
0x180006d29  mov     [rbp+30h+var_20], rax
0x180006d2d  mov     [rbp+30h+var_88], 2
0x180006d34  mov     [rbp+30h+var_6C], ebx
0x180006d37  mov     [rbp+30h+var_68], rbx
0x180006d3b  mov     [rbp+30h+var_60], 11h
0x180006d42  mov     [rbp+30h+var_5C], 1
0x180006d49  mov     [rbp+30h+var_50], 2
0x180006d50  movups  [rbp+30h+var_48], xmm0
0x180006d54  mov     [rbp+30h+var_34], ebx
0x180006d57  mov     [rbp+30h+var_30], rbx
0x180006d5b  mov     [rbp+30h+var_28], 0Dh
0x180006d62  mov     [rbp+30h+var_24], 10h
0x180006d69  call    cs:__imp_CreateEventW
0x180006d70  nop     dword ptr [rax+rax+00h]
0x180006d75  mov     rdi, rax
0x180006d78  test    rax, rax
0x180006d7b  jnz     short loc_180006DA1
0x180006d7d  call    cs:__imp_GetLastError
0x180006d84  nop     dword ptr [rax+rax+00h]
0x180006d89  mov     ebx, eax
0x180006d8b  test    eax, eax
0x180006d8d  jle     loc_180006E31
0x180006d93  movzx   ebx, ax
0x180006d96  or      ebx, 80070000h
0x180006d9c  jmp     loc_180006E31
0x180006da1  lea     rax, [rsp+130h+var_E0]
0x180006da6  mov     qword ptr [rsp+130h+var_D8], rdi
0x180006dab  mov     [rsp+130h+var_F0], rax
0x180006db0  mov     edx, 1
0x180006db5  lea     rax, [rsp+130h+var_D8]
0x180006dba  mov     dword ptr [rsp+130h+var_D8+8], ebx
0x180006dbe  mov     [rsp+130h+var_F8], rax
0x180006dc3  xor     r9d, r9d
0x180006dc6  lea     rax, DevQueryCallback
0x180006dcd  xor     r8d, r8d
0x180006dd0  mov     [rsp+130h+var_100], rax
0x180006dd5  mov     ecx, edx
0x180006dd7  lea     rax, [rsp+130h+var_C0]
0x180006ddc  mov     [rsp+130h+var_108], rax
0x180006de1  mov     [rsp+130h+var_110], 3
0x180006de9  call    cs:__imp_DevCreateObjectQuery
0x180006df0  nop     dword ptr [rax+rax+00h]
0x180006df5  mov     ebx, eax
0x180006df7  test    eax, eax
0x180006df9  js      short loc_180006E31
0x180006dfb  mov     edx, 7530h; dwMilliseconds
0x180006e00  mov     rcx, rdi; hHandle
0x180006e03  call    cs:__imp_WaitForSingleObject
0x180006e0a  nop     dword ptr [rax+rax+00h]
0x180006e0f  test    eax, eax
0x180006e11  jnz     short loc_180006E19
0x180006e13  mov     ebx, dword ptr [rsp+130h+var_D8+8]
0x180006e17  jmp     short loc_180006E31
0x180006e19  cmp     eax, 0FFFFFFFFh
0x180006e1c  jz      loc_180006D7D
0x180006e22  cmp     eax, 102h
0x180006e27  mov     ebx, 8000FFFFh
0x180006e2c  cmovz   ebx, dword ptr [rsp+130h+var_D8+8]
0x180006e31  mov     rcx, [rsp+130h+var_E0]
0x180006e36  test    rcx, rcx
0x180006e39  jz      short loc_180006E47
0x180006e3b  call    cs:__imp_DevCloseObjectQuery
0x180006e42  nop     dword ptr [rax+rax+00h]
0x180006e47  test    rdi, rdi
0x180006e4a  jz      short loc_180006E5B
0x180006e4c  mov     rcx, rdi; hObject
0x180006e4f  call    cs:__imp_CloseHandle
0x180006e56  nop     dword ptr [rax+rax+00h]
0x180006e5b  mov     eax, ebx
0x180006e5d  mov     rcx, [rbp+30h+var_10]
0x180006e61  xor     rcx, rsp; StackCookie
0x180006e64  call    __security_check_cookie
0x180006e69  lea     r11, [rsp+130h+var_s0]
0x180006e71  mov     rbx, [r11+10h]
0x180006e75  mov     rdi, [r11+18h]
0x180006e79  mov     rsp, r11
0x180006e7c  pop     rbp
0x180006e7d  retn
```
