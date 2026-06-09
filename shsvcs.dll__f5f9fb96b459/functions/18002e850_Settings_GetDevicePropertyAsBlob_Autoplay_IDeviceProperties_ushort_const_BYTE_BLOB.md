# Settings::GetDevicePropertyAsBlob(Autoplay::IDeviceProperties *,ushort const *,_BYTE_BLOB * *)

- ea: `0x18002e850`
- end: `0x18002e8ee`
- name: `?GetDevicePropertyAsBlob@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAPEAU_BYTE_BLOB@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(Settings *this, struct Autoplay::IDeviceProperties *, unsigned __int16 *, struct _BYTE_BLOB **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b660`

## callees

- `0x180005010`
- `0x1800055b4`
- `0x18002e850`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e891`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e891`

## pseudocode

```c
__int64 __fastcall Settings::GetDevicePropertyAsBlob(
        Settings *this,
        struct Autoplay::IDeviceProperties *a2,
        unsigned __int16 *a3,
        struct _BYTE_BLOB **a4)
{
  int DevicePropertySize; // eax
  int DevicePropertyGeneric; // edi
  _DWORD *v9; // rax
  void *v10; // rbx
  int v11; // ecx
  unsigned __int8 *v13; // [rsp+20h] [rbp-28h]
  unsigned __int8 *v14; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(v14) = 0;
  DevicePropertySize = Settings::_GetDevicePropertySize(this, a2, (const unsigned __int16 *)&v14, (unsigned int *)a4);
  *(_QWORD *)a3 = 0;
  DevicePropertyGeneric = DevicePropertySize;
  if ( DevicePropertySize >= 0 )
  {
    v9 = CoTaskMemAlloc((unsigned int)v14 + 8LL);
    v10 = v9;
    if ( v9 )
    {
      v11 = (int)v14;
      *v9 = (_DWORD)v14;
      LODWORD(v13) = v11;
      DevicePropertyGeneric = Settings::_GetDevicePropertyGeneric(
                                this,
                                a2,
                                (const unsigned __int16 *)3,
                                (__int64)(v9 + 1),
                                v13);
      if ( DevicePropertyGeneric < 0 )
        CoTaskMemFree(v10);
      else
        *(_QWORD *)a3 = v10;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)DevicePropertyGeneric;
}

```

## disassembly

```asm
0x18002e850  mov     rax, rsp
0x18002e853  mov     [rax+8], rbx
0x18002e857  mov     [rax+10h], rbp
0x18002e85b  push    rsi
0x18002e85c  push    rdi
0x18002e85d  push    r14
0x18002e85f  sub     rsp, 30h
0x18002e863  mov     rsi, r8
0x18002e866  mov     dword ptr [rax+18h], 0
0x18002e86d  lea     r8, [rax+18h]; unsigned __int16 *
0x18002e871  mov     rbp, rdx
0x18002e874  mov     r14, rcx
0x18002e877  call    ?_GetDevicePropertySize@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAK@Z; Settings::_GetDevicePropertySize(Autoplay::IDeviceProperties *,ushort const *,ulong *)
0x18002e87c  mov     qword ptr [rsi], 0
0x18002e883  mov     edi, eax
0x18002e885  test    eax, eax
0x18002e887  js      short loc_18002E8D9
0x18002e889  mov     ecx, dword ptr [rsp+48h+arg_10]
0x18002e88d  add     rcx, 8; cb
0x18002e891  call    cs:__imp_CoTaskMemAlloc
0x18002e897  mov     rbx, rax
0x18002e89a  test    rax, rax
0x18002e89d  jz      short loc_18002E8D4
0x18002e89f  mov     ecx, dword ptr [rsp+48h+arg_10]
0x18002e8a3  lea     r9, [rax+4]; unsigned int
0x18002e8a7  mov     [rax], ecx
0x18002e8a9  mov     r8d, 3; unsigned __int16 *
0x18002e8af  mov     dword ptr [rsp+48h+var_28], ecx; unsigned __int8 *
0x18002e8b3  mov     rdx, rbp; struct Autoplay::IDeviceProperties *
0x18002e8b6  mov     rcx, r14; this
0x18002e8b9  call    ?_GetDevicePropertyGeneric@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z; Settings::_GetDevicePropertyGeneric(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)
0x18002e8be  mov     edi, eax
0x18002e8c0  test    eax, eax
0x18002e8c2  js      short loc_18002E8C9
0x18002e8c4  mov     [rsi], rbx
0x18002e8c7  jmp     short loc_18002E8D9
0x18002e8c9  mov     rcx, rbx; pv
0x18002e8cc  call    cs:__imp_CoTaskMemFree
0x18002e8d2  jmp     short loc_18002E8D9
0x18002e8d4  mov     edi, 8007000Eh
0x18002e8d9  mov     rbx, [rsp+48h+arg_0]
0x18002e8de  mov     eax, edi
0x18002e8e0  mov     rbp, [rsp+48h+arg_8]
0x18002e8e5  add     rsp, 30h
0x18002e8e9  pop     r14
0x18002e8eb  pop     rdi
0x18002e8ec  pop     rsi
0x18002e8ed  retn
```
