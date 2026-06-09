# CUsbCeipTask::Worker(void)

- ea: `0x180003b40`
- end: `0x180003b68`
- name: `?Worker@CUsbCeipTask@@EEAAJXZ`
- size: `40`
- prototype: `__int64 __fastcall(CUsbCeipTask *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003b40`
- `0x180005da0`
- `0x1800064b0`

## pseudocode

```c
__int64 __fastcall CUsbCeipTask::Worker(CUsbCeipTask *this)
{
  int v2; // ecx
  int v3; // ecx
  unsigned int v4; // eax
  CException *v5; // [rsp+20h] [rbp-18h] BYREF
  _com_error *v6; // [rsp+28h] [rbp-10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+10h]

  v7 = 0;
  try
  {
    UsbCeip_Execute(0);
    UpdateLastRunTimeStamp();
  }
  catch ( CException *v5 )
  {
    v2 = *((_DWORD *)v5 + 1);
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        if ( v3 != 1 )
          return (unsigned int)-2147467259;
        return *(_DWORD *)v5 | 0x10000000u;
      }
      else
      {
        return *(unsigned int *)v5;
      }
    }
    else
    {
      v4 = *(_DWORD *)v5;
      if ( *(int *)v5 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
    }
    return v4;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( _com_error *v6 )
  {
    return *((unsigned int *)v6 + 2);
  }
  UsbCeip_Execute(0);
}

```

## disassembly

```asm
0x180003b40  sub     rsp, 38h
0x180003b44  mov     [rsp+38h+arg_8], 0
0x180003b4c  xor     ecx, ecx; unsigned __int8
0x180003b4e  call    ?UsbCeip_Execute@@YAXE@Z; UsbCeip_Execute(uchar)
0x180003b53  call    ?UpdateLastRunTimeStamp@@YAXXZ; UpdateLastRunTimeStamp(void)
0x180003b58  nop
0x180003b59  jmp     short loc_180003B5F
0x180003b5b  jmp     short loc_180003B5F
0x180003b5d  jmp     short $+2
0x180003b5f  mov     eax, [rsp+38h+arg_8]
0x180003b63  add     rsp, 38h
0x180003b67  retn
```
