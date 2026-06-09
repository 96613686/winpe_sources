# CTrkWksSvc::ServiceHandler(ulong,ulong,void *,void *)

- ea: `0x18000bba0`
- end: `0x18000bd1c`
- name: `?ServiceHandler@CTrkWksSvc@@UEAAKKKPEAX0@Z`
- size: `380`
- prototype: `__int64 __fastcall(HANDLE *this, int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000bba0`
- `0x18000bd24`

## import_xrefs

- `ntdll!NtClearEvent` at `0x18000bd14`
- `ntdll!NtClearEvent` at `0x18000bd14`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bcdf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bcdf`

## pseudocode

```c
__int64 __fastcall CTrkWksSvc::ServiceHandler(HANDLE *this, int a2, int a3, _DWORD *a4)
{
  int v4; // edx
  int v5; // edx
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  char *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax

  v4 = a2 - 1;
  if ( v4 && (v5 = v4 - 4) != 0 )
  {
    if ( v5 != 6 )
      return 0;
    v7 = a3 - 32769;
    if ( !v7 )
      goto LABEL_38;
    v8 = v7 - 1;
    if ( !v8 )
    {
      if ( a4[1] != 6 )
        return 0;
      v12 = 5;
      goto LABEL_17;
    }
    v9 = v8 - 2;
    if ( !v9 )
    {
LABEL_38:
      if ( a4[1] != 6 )
        return 0;
      goto LABEL_26;
    }
    if ( v9 == 2 && a4[1] == 6 )
    {
      v10 = *((_QWORD *)a4 + 4) - *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1;
      if ( !v10 )
        v10 = *((_QWORD *)a4 + 5) - *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4;
      if ( !v10 )
      {
        v13 = (char *)(this + 72);
        v12 = 0;
        goto LABEL_18;
      }
      v11 = *((_QWORD *)a4 + 4) - *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1;
      if ( !v11 )
        v11 = *((_QWORD *)a4 + 5) - *(_QWORD *)GUID_IO_VOLUME_UNLOCK.Data4;
      if ( !v11 )
      {
        v12 = 1;
LABEL_17:
        v13 = (char *)(this + 72);
LABEL_18:
        CVolumeManager::VolumeDeviceEvent(v13, *((_QWORD *)a4 + 3), v12);
        return 0;
      }
      v14 = *((_QWORD *)a4 + 4) - *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1;
      if ( !v14 )
        v14 = *((_QWORD *)a4 + 5) - *(_QWORD *)GUID_IO_VOLUME_LOCK_FAILED.Data4;
      if ( !v14 )
      {
        v12 = 2;
        goto LABEL_17;
      }
      v15 = *((_QWORD *)a4 + 4) - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1;
      if ( !v15 )
        v15 = *((_QWORD *)a4 + 5) - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4;
      if ( !v15 )
      {
LABEL_26:
        v12 = 4;
        goto LABEL_17;
      }
      v16 = *((_QWORD *)a4 + 4) - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
      if ( !v16 )
        v16 = *((_QWORD *)a4 + 5) - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
      if ( !v16 )
      {
        v12 = 3;
        goto LABEL_17;
      }
    }
  }
  else
  {
    if ( ((_BYTE)this[49] & 1) != 0 )
      NtClearEvent(this[53]);
    if ( g_stopServiceEvent )
      SetEvent(g_stopServiceEvent);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bba0  sub     rsp, 28h
0x18000bba4  sub     edx, 1
0x18000bba7  jz      loc_18000BCC6
0x18000bbad  mov     r10d, 4
0x18000bbb3  sub     edx, r10d
0x18000bbb6  jz      loc_18000BCC6
0x18000bbbc  cmp     edx, 6
0x18000bbbf  jz      short loc_18000BBC8
0x18000bbc1  xor     eax, eax
0x18000bbc3  add     rsp, 28h
0x18000bbc7  retn
0x18000bbc8  sub     r8d, 8001h
0x18000bbcf  jz      loc_18000BD00
0x18000bbd5  sub     r8d, 1
0x18000bbd9  jz      loc_18000BCEA
0x18000bbdf  sub     r8d, 2
0x18000bbe3  jz      loc_18000BD00
0x18000bbe9  cmp     r8d, 2
0x18000bbed  jnz     short loc_18000BBC1
0x18000bbef  cmp     dword ptr [r9+4], 6
0x18000bbf4  jnz     short loc_18000BBC1
0x18000bbf6  mov     rax, [r9+20h]
0x18000bbfa  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data1
0x18000bc01  jnz     short loc_18000BC0E
0x18000bc03  mov     rax, [r9+28h]
0x18000bc07  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data4
0x18000bc0e  test    rax, rax
0x18000bc11  jz      short loc_18000BC49
0x18000bc13  mov     rax, [r9+20h]
0x18000bc17  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data1
0x18000bc1e  jnz     short loc_18000BC2B
0x18000bc20  mov     rax, [r9+28h]
0x18000bc24  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data4
0x18000bc2b  test    rax, rax
0x18000bc2e  jnz     short loc_18000BC55
0x18000bc30  lea     r8d, [rax+1]
0x18000bc34  add     rcx, 240h
0x18000bc3b  mov     rdx, [r9+18h]
0x18000bc3f  call    ?VolumeDeviceEvent@CVolumeManager@@AEAAXPEAXW4EVolumeDeviceEvent@1@@Z; CVolumeManager::VolumeDeviceEvent(void *,CVolumeManager::EVolumeDeviceEvent)
0x18000bc44  jmp     loc_18000BBC1
0x18000bc49  add     rcx, 240h
0x18000bc50  xor     r8d, r8d
0x18000bc53  jmp     short loc_18000BC3B
0x18000bc55  mov     rax, [r9+20h]
0x18000bc59  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data1
0x18000bc60  jnz     short loc_18000BC6D
0x18000bc62  mov     rax, [r9+28h]
0x18000bc66  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data4
0x18000bc6d  test    rax, rax
0x18000bc70  jz      short loc_18000BC94
0x18000bc72  mov     rax, [r9+20h]
0x18000bc76  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x18000bc7d  jnz     short loc_18000BC8A
0x18000bc7f  mov     rax, [r9+28h]
0x18000bc83  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x18000bc8a  test    rax, rax
0x18000bc8d  jnz     short loc_18000BC9C
0x18000bc8f  mov     r8d, r10d
0x18000bc92  jmp     short loc_18000BC34
0x18000bc94  mov     r8d, 2
0x18000bc9a  jmp     short loc_18000BC34
0x18000bc9c  mov     rax, [r9+20h]
0x18000bca0  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x18000bca7  jnz     short loc_18000BCB4
0x18000bca9  mov     rax, [r9+28h]
0x18000bcad  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x18000bcb4  test    rax, rax
0x18000bcb7  jnz     loc_18000BBC1
0x18000bcbd  lea     r8d, [rax+3]
0x18000bcc1  jmp     loc_18000BC34
0x18000bcc6  test    byte ptr [rcx+188h], 1
0x18000bccd  jnz     short loc_18000BD0D
0x18000bccf  mov     rcx, cs:?g_stopServiceEvent@@3PEAXEA; hEvent
0x18000bcd6  test    rcx, rcx
0x18000bcd9  jz      loc_18000BBC1
0x18000bcdf  call    cs:__imp_SetEvent
0x18000bce5  jmp     loc_18000BBC1
0x18000bcea  cmp     dword ptr [r9+4], 6
0x18000bcef  jnz     loc_18000BBC1
0x18000bcf5  mov     r8d, 5
0x18000bcfb  jmp     loc_18000BC34
0x18000bd00  cmp     dword ptr [r9+4], 6
0x18000bd05  jnz     loc_18000BBC1
0x18000bd0b  jmp     short loc_18000BC8F
0x18000bd0d  mov     rcx, [rcx+1A8h]; EventHandle
0x18000bd14  call    cs:__imp_NtClearEvent
0x18000bd1a  jmp     short loc_18000BCCF
```
