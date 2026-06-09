# RtmMarkDestForChangeNotification

- ea: `0x180003f10`
- end: `0x180003f9f`
- name: `RtmMarkDestForChangeNotification`
- size: `143`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_NOTIFY_HANDLE NotifyHandle, RTM_DEST_HANDLE DestHandle, BOOL MarkDest)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800151ec`
- `0x180015a8c`
- `0x180015f54`
- `0x180016d00`

## callees

- `0x180003f10`
- `0x180014d2c`
- `0x180015178`

## pseudocode

```c
DWORD __stdcall RtmMarkDestForChangeNotification(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_NOTIFY_HANDLE NotifyHandle,
        RTM_DEST_HANDLE DestHandle,
        BOOL MarkDest)
{
  unsigned __int64 v4; // rsi
  signed int v5; // ecx
  unsigned __int64 v6; // rdi
  int v7; // eax

  v4 = (unsigned __int64)NotifyHandle ^ 0x7754DF32;
  if ( (unsigned __int64)NotifyHandle != 0x7754DF32 )
  {
    v5 = *(_DWORD *)(((unsigned __int64)NotifyHandle ^ 0x7754DF32) + 0x1C);
    if ( v5 >= 0 )
    {
      v6 = (unsigned __int64)DestHandle ^ 0x7754DF32;
      if ( (unsigned __int64)DestHandle != 0x7754DF32 )
      {
        v7 = *(_DWORD *)(((unsigned __int64)DestHandle ^ 0x7754DF32) + 0x28);
        if ( _bittest(&v7, v5) )
        {
          if ( !MarkDest )
          {
            AcquireWriteLock((_QWORD *)(v6 + 32));
            *(_DWORD *)(v6 + 40) &= ~(1 << *(_DWORD *)(v4 + 28));
LABEL_9:
            ReleaseWriteLock(v6 + 32);
          }
        }
        else if ( MarkDest )
        {
          AcquireWriteLock((_QWORD *)(v6 + 32));
          *(_DWORD *)(v6 + 40) |= 1 << *(_DWORD *)(v4 + 28);
          goto LABEL_9;
        }
        return 0;
      }
    }
  }
  return 6;
}

```

## disassembly

```asm
0x180003f10  mov     [rsp+arg_0], rbx
0x180003f15  mov     [rsp+arg_8], rsi
0x180003f1a  push    rdi
0x180003f1b  sub     rsp, 20h
0x180003f1f  mov     rsi, rdx
0x180003f22  mov     eax, 7754DF32h
0x180003f27  xor     rsi, rax
0x180003f2a  mov     rdi, r8
0x180003f2d  jz      short loc_180003F8A
0x180003f2f  mov     ecx, [rsi+1Ch]
0x180003f32  test    ecx, ecx
0x180003f34  js      short loc_180003F8A
0x180003f36  xor     rdi, rax
0x180003f39  jz      short loc_180003F8A
0x180003f3b  mov     eax, [rdi+28h]
0x180003f3e  bt      eax, ecx
0x180003f41  jnb     short loc_180003F62
0x180003f43  test    r9d, r9d
0x180003f46  jnz     short loc_180003F86
0x180003f48  lea     rcx, [rdi+20h]
0x180003f4c  call    AcquireWriteLock
0x180003f51  mov     ecx, [rsi+1Ch]
0x180003f54  mov     eax, 1
0x180003f59  shl     eax, cl
0x180003f5b  not     eax
0x180003f5d  and     [rdi+28h], eax
0x180003f60  jmp     short loc_180003F7D
0x180003f62  test    r9d, r9d
0x180003f65  jz      short loc_180003F86
0x180003f67  lea     rcx, [rdi+20h]
0x180003f6b  call    AcquireWriteLock
0x180003f70  mov     ecx, [rsi+1Ch]
0x180003f73  mov     eax, 1
0x180003f78  shl     eax, cl
0x180003f7a  or      [rdi+28h], eax
0x180003f7d  lea     rcx, [rdi+20h]
0x180003f81  call    ReleaseWriteLock
0x180003f86  xor     eax, eax
0x180003f88  jmp     short loc_180003F8F
0x180003f8a  mov     eax, 6
0x180003f8f  mov     rbx, [rsp+28h+arg_0]
0x180003f94  mov     rsi, [rsp+28h+arg_8]
0x180003f99  add     rsp, 20h
0x180003f9d  pop     rdi
0x180003f9e  retn
```
