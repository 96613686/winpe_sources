# CDeviceQueryWrapper::Initialize(PnPServices::IPnPInterfaceEventCB *)

- ea: `0x18002f1ac`
- end: `0x18002f296`
- name: `?Initialize@CDeviceQueryWrapper@@QEAAJPEAVIPnPInterfaceEventCB@PnPServices@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(CDeviceQueryWrapper *__hidden this, struct PnPServices::IPnPInterfaceEventCB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18002e4c0`

## callees

- `0x18001c2d0`
- `0x18002f1ac`
- `0x18002f904`
- `0x180032c90`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18002f268`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18002f268`

## pseudocode

```c
__int64 __fastcall CDeviceQueryWrapper::Initialize(
        CDeviceQueryWrapper *this,
        struct PnPServices::IPnPInterfaceEventCB *a2)
{
  int v4; // ebx
  char v6; // [rsp+50h] [rbp-19h] BYREF
  __int64 v7; // [rsp+58h] [rbp-11h] BYREF
  __int128 v8; // [rsp+60h] [rbp-9h]
  int v9; // [rsp+70h] [rbp+7h]
  int v10; // [rsp+74h] [rbp+Bh]
  __int64 v11; // [rsp+78h] [rbp+Fh]
  int v12; // [rsp+80h] [rbp+17h]
  int v13; // [rsp+84h] [rbp+1Bh]
  char *v14; // [rsp+88h] [rbp+1Fh]

  v4 = CCritSectWithResource<CDummyResource>::Init((char *)this + 168);
  if ( v4 < 0 )
    goto LABEL_3;
  *((_QWORD *)this + 2) = a2;
  _InterlockedAdd((volatile signed __int32 *)a2 + 2, 1u);
  v9 = 4;
  v6 = -1;
  v14 = &v6;
  v7 = 2;
  v8 = DEVPKEY_DeviceSetup_AutoplayReady;
  v10 = 0;
  v11 = 0;
  v12 = 17;
  v13 = 1;
  v4 = DevCreateObjectQuery(2, 1, 0, 0, 1, &v7, CDeviceQueryWrapper::ContainerCallback, 0, (char *)this + 224);
  if ( v4 < 0 )
LABEL_3:
    CDeviceQueryWrapper::Shutdown(this);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f1ac  push    rbp
0x18002f1ae  push    rbx
0x18002f1af  push    rsi
0x18002f1b0  push    rdi
0x18002f1b1  lea     rbp, [rsp-3Fh]
0x18002f1b6  sub     rsp, 0A8h
0x18002f1bd  mov     rax, cs:__security_cookie
0x18002f1c4  xor     rax, rsp
0x18002f1c7  mov     [rbp+57h+var_30], rax
0x18002f1cb  mov     rdi, rcx
0x18002f1ce  mov     rsi, rdx
0x18002f1d1  add     rcx, 0A8h
0x18002f1d8  call    ?Init@?$CCritSectWithResource@VCDummyResource@@@@QEAAJXZ; CCritSectWithResource<CDummyResource>::Init(void)
0x18002f1dd  mov     ebx, eax
0x18002f1df  test    eax, eax
0x18002f1e1  js      loc_18002F274
0x18002f1e7  mov     [rdi+10h], rsi
0x18002f1eb  mov     edx, 1
0x18002f1f0  lock add [rsi+8], edx
0x18002f1f4  mov     eax, cs:dword_1800382C8
0x18002f1fa  lea     ecx, [rdx+1]
0x18002f1fd  movups  xmm0, cs:DEVPKEY_DeviceSetup_AutoplayReady
0x18002f204  mov     [rbp+57h+var_50], eax
0x18002f207  xor     r9d, r9d
0x18002f20a  lea     rax, [rbp+57h+var_70]
0x18002f20e  mov     [rbp+57h+var_70], 0FFh
0x18002f212  mov     [rbp+57h+var_38], rax
0x18002f216  xor     r8d, r8d
0x18002f219  lea     rax, [rdi+0E0h]
0x18002f220  mov     [rbp+57h+var_68], rcx
0x18002f224  mov     [rsp+0C0h+var_80], rax
0x18002f229  lea     rax, ?ContainerCallback@CDeviceQueryWrapper@@SAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CDeviceQueryWrapper::ContainerCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18002f230  mov     [rsp+0C0h+var_88], 0
0x18002f239  mov     [rsp+0C0h+var_90], rax
0x18002f23e  lea     rax, [rbp+57h+var_68]
0x18002f242  mov     [rsp+0C0h+var_98], rax
0x18002f247  mov     [rsp+0C0h+var_A0], edx
0x18002f24b  movups  [rbp+57h+var_60], xmm0
0x18002f24f  mov     [rbp+57h+var_4C], 0
0x18002f256  mov     [rbp+57h+var_48], 0
0x18002f25e  mov     [rbp+57h+var_40], 11h
0x18002f265  mov     [rbp+57h+var_3C], edx
0x18002f268  call    cs:__imp_DevCreateObjectQuery
0x18002f26e  mov     ebx, eax
0x18002f270  test    eax, eax
0x18002f272  jns     short loc_18002F27C
0x18002f274  mov     rcx, rdi; this
0x18002f277  call    ?Shutdown@CDeviceQueryWrapper@@QEAAXXZ; CDeviceQueryWrapper::Shutdown(void)
0x18002f27c  mov     eax, ebx
0x18002f27e  mov     rcx, [rbp+57h+var_30]
0x18002f282  xor     rcx, rsp; StackCookie
0x18002f285  call    __security_check_cookie
0x18002f28a  add     rsp, 0A8h
0x18002f291  pop     rdi
0x18002f292  pop     rsi
0x18002f293  pop     rbx
0x18002f294  pop     rbp
0x18002f295  retn
```
