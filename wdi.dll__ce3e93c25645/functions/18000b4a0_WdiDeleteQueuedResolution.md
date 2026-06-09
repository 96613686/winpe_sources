# WdiDeleteQueuedResolution

- ea: `0x18000b4a0`
- end: `0x18000b5b3`
- name: `WdiDeleteQueuedResolution`
- size: `275`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002ba0`
- `0x18000a280`
- `0x18000b4a0`

## string_xrefs

- `0x18000b598`: `WdiDeleteQueuedResolution`

## pseudocode

```c
__int64 __fastcall WdiDeleteQueuedResolution(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // rdx
  int v5; // eax
  int Args; // eax

  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 168) )
    {
      if ( *(_DWORD *)(a1 + 16) == 1 )
      {
        if ( (_InterlockedExchange((volatile __int32 *)(a1 + 108), *(_DWORD *)(a1 + 108)) & 2) != 0 )
        {
          v2 = -2147020579;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
            (int)L"WdiDeleteQueuedResolution",
            600,
            (int)L"Error = %d",
            221);
        }
        else if ( a2 < *(_DWORD *)(a1 + 156) )
        {
          v3 = *(_QWORD *)(a1 + 168);
          v4 = 104LL * a2;
          v5 = *(_DWORD *)(v4 + v3 + 68);
          if ( (v5 & 2) != 0 )
          {
            v2 = -2147020579;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiDeleteQueuedResolution",
              617,
              (int)L"Error = %d",
              221);
          }
          else
          {
            *(_DWORD *)(v4 + v3 + 68) = v5 | 2;
            Args = WdipSendClientDeleteQueuedResolutionMessage(a1, *(_QWORD *)(a1 + 168) + v4);
            v2 = Args;
            if ( Args < 0 )
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                (int)L"WdiDeleteQueuedResolution",
                626,
                (int)L"Error = %d",
                Args);
          }
        }
        else
        {
          v2 = -2147024809;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
            (int)L"WdiDeleteQueuedResolution",
            607,
            (int)L"Error = %d",
            87);
        }
      }
      else
      {
        v2 = -2147020579;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
          (int)L"WdiDeleteQueuedResolution",
          596,
          (int)L"Error = %d",
          221);
      }
    }
    else
    {
      v2 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
        (int)L"WdiDeleteQueuedResolution",
        592,
        (int)L"Error = %d",
        87);
    }
  }
  else
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiDeleteQueuedResolution",
      591,
      (int)L"Error = %d",
      87);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b4a0  push    rbx
0x18000b4a2  sub     rsp, 30h
0x18000b4a6  test    rcx, rcx
0x18000b4a9  jnz     short loc_18000B4C3
0x18000b4ab  mov     ebx, 80070057h
0x18000b4b0  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x18000b4b8  mov     r8d, 24Fh
0x18000b4be  jmp     loc_18000B591
0x18000b4c3  cmp     qword ptr [rcx+0A8h], 0
0x18000b4cb  jnz     short loc_18000B4E5
0x18000b4cd  mov     ebx, 80070057h
0x18000b4d2  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x18000b4da  mov     r8d, 250h
0x18000b4e0  jmp     loc_18000B591
0x18000b4e5  cmp     dword ptr [rcx+10h], 1
0x18000b4e9  jz      short loc_18000B503
0x18000b4eb  mov     ebx, 800710DDh
0x18000b4f0  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000b4f8  mov     r8d, 254h
0x18000b4fe  jmp     loc_18000B591
0x18000b503  mov     eax, [rcx+6Ch]
0x18000b506  xchg    eax, [rcx+6Ch]
0x18000b509  test    al, 2
0x18000b50b  jz      short loc_18000B522
0x18000b50d  mov     ebx, 800710DDh
0x18000b512  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000b51a  mov     r8d, 258h
0x18000b520  jmp     short loc_18000B591
0x18000b522  cmp     edx, [rcx+9Ch]
0x18000b528  jb      short loc_18000B53F
0x18000b52a  mov     ebx, 80070057h
0x18000b52f  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x18000b537  mov     r8d, 25Fh
0x18000b53d  jmp     short loc_18000B591
0x18000b53f  mov     r8, [rcx+0A8h]
0x18000b546  mov     eax, edx
0x18000b548  imul    rdx, rax, 68h ; 'h'
0x18000b54c  mov     eax, [rdx+r8+44h]
0x18000b551  test    al, 2
0x18000b553  jz      short loc_18000B56A
0x18000b555  mov     ebx, 800710DDh
0x18000b55a  mov     dword ptr [rsp+38h+Args], 10DDh
0x18000b562  mov     r8d, 269h
0x18000b568  jmp     short loc_18000B591
0x18000b56a  or      eax, 2
0x18000b56d  mov     [rdx+r8+44h], eax
0x18000b572  add     rdx, [rcx+0A8h]
0x18000b579  call    WdipSendClientDeleteQueuedResolutionMessage
0x18000b57e  mov     ebx, eax
0x18000b580  test    eax, eax
0x18000b582  jns     short loc_18000B5AB
0x18000b584  movzx   ecx, ax
0x18000b587  mov     r8d, 272h; int
0x18000b58d  mov     dword ptr [rsp+38h+Args], ecx; Args
0x18000b591  lea     r9, aErrorD_0; "Error = %d"
0x18000b598  lea     rdx, aWdideletequeue_0; "WdiDeleteQueuedResolution"
0x18000b59f  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b5a6  call    WdipTraceError
0x18000b5ab  mov     eax, ebx
0x18000b5ad  add     rsp, 30h
0x18000b5b1  pop     rbx
0x18000b5b2  retn
```
