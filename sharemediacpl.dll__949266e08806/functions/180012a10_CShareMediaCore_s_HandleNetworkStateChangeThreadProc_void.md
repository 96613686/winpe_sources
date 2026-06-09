# CShareMediaCore::s_HandleNetworkStateChangeThreadProc(void *)

- ea: `0x180012a10`
- end: `0x180012bcd`
- name: `?s_HandleNetworkStateChangeThreadProc@CShareMediaCore@@CAKPEAX@Z`
- size: `445`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003860`
- `0x180003888`
- `0x18000ae94`
- `0x18000afa8`
- `0x180012a10`
- `0x18001e010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180012b6d`
- `KERNEL32!CloseHandle` at `0x180012b6d`
- `KERNEL32!WaitForSingleObject` at `0x180012b2c`
- `KERNEL32!WaitForSingleObject` at `0x180012b2c`
- `KERNEL32!CreateEventW` at `0x180012aac`
- `KERNEL32!CreateEventW` at `0x180012aac`
- `KERNEL32!GetLastError` at `0x180012abe`
- `KERNEL32!GetLastError` at `0x180012abe`
- `ole32!CoUninitialize` at `0x180012b8d`
- `ole32!CoUninitialize` at `0x180012b8d`
- `ole32!CoInitializeEx` at `0x180012a55`
- `ole32!CoInitializeEx` at `0x180012a55`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::s_HandleNetworkStateChangeThreadProc(unsigned int *Parameter)
{
  int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v7; // esi
  int v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = CoInitializeEx(0, 2u);
  if ( v2 >= 0 )
  {
    if ( Parameter )
    {
      v3 = *((_QWORD *)Parameter + 5);
      v4 = Parameter[12];
      v10 = 0;
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v3 + 40LL))(
             v3,
             v4,
             &GUID_595d6e65_732c_4736_853f_db64f5aa1eec,
             &v10);
      if ( v2 >= 0 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)Parameter + 22) = EventW;
        if ( EventW )
          goto LABEL_11;
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_11:
          v7 = 0;
          do
          {
            v9 = 0;
            v2 = IsNetworkConnected(&v9);
            if ( v2 >= 0 )
            {
              if ( !v9 || (v9 = 0, v2 = IsNetworkInitialized(&v9), v2 >= 0) && v9 )
                v7 = 1;
            }
          }
          while ( WaitForSingleObject(*((HANDLE *)Parameter + 22), 0x3E8u) && !v7 );
          if ( v2 >= 0 && v7 )
            v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          CloseHandle(*((HANDLE *)Parameter + 22));
          *((_QWORD *)Parameter + 22) = 0;
        }
      }
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)Parameter + 16LL))(Parameter);
    }
    CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v2);
  return 0;
}

```

## disassembly

```asm
0x180012a10  mov     [rsp+arg_0], rbx
0x180012a15  push    rsi
0x180012a16  push    rdi
0x180012a17  push    r15
0x180012a19  sub     rsp, 30h
0x180012a1d  mov     rdi, rcx
0x180012a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a27  lea     r15, WPP_GLOBAL_Control
0x180012a2e  cmp     rcx, r15
0x180012a31  jz      short loc_180012A4E
0x180012a33  test    byte ptr [rcx+1Ch], 20h
0x180012a37  jz      short loc_180012A4E
0x180012a39  mov     rcx, [rcx+10h]
0x180012a3d  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180012a44  mov     edx, 5Ah ; 'Z'
0x180012a49  call    WPP_SF_
0x180012a4e  mov     edx, 2; dwCoInit
0x180012a53  xor     ecx, ecx; pvReserved
0x180012a55  call    cs:__imp_CoInitializeEx
0x180012a5b  mov     ebx, eax
0x180012a5d  test    eax, eax
0x180012a5f  js      loc_180012B93
0x180012a65  test    rdi, rdi
0x180012a68  jz      loc_180012B8D
0x180012a6e  mov     rcx, [rdi+28h]
0x180012a72  lea     r9, [rsp+48h+arg_10]
0x180012a77  mov     edx, [rdi+30h]
0x180012a7a  lea     r8, _GUID_595d6e65_732c_4736_853f_db64f5aa1eec
0x180012a81  mov     [rsp+48h+arg_10], 0
0x180012a8a  mov     rax, [rcx]
0x180012a8d  mov     rax, [rax+28h]
0x180012a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a96  mov     ebx, eax
0x180012a98  test    eax, eax
0x180012a9a  js      loc_180012B7E
0x180012aa0  xor     r9d, r9d; lpName
0x180012aa3  xor     r8d, r8d; bInitialState
0x180012aa6  xor     ecx, ecx; lpEventAttributes
0x180012aa8  lea     edx, [r9+1]; bManualReset
0x180012aac  call    cs:__imp_CreateEventW
0x180012ab2  mov     [rdi+0B0h], rax
0x180012ab9  test    rax, rax
0x180012abc  jnz     short loc_180012ADB
0x180012abe  call    cs:__imp_GetLastError
0x180012ac4  mov     ebx, eax
0x180012ac6  test    eax, eax
0x180012ac8  jle     short loc_180012AD3
0x180012aca  movzx   ebx, ax
0x180012acd  or      ebx, 80070000h
0x180012ad3  test    ebx, ebx
0x180012ad5  js      loc_180012B7E
0x180012adb  xor     esi, esi
0x180012add  lea     rcx, [rsp+48h+arg_8]; int *
0x180012ae2  mov     [rsp+48h+arg_8], 0
0x180012aea  call    ?IsNetworkConnected@@YAJPEAH@Z; IsNetworkConnected(int *)
0x180012aef  mov     ebx, eax
0x180012af1  test    eax, eax
0x180012af3  js      short loc_180012B20
0x180012af5  cmp     [rsp+48h+arg_8], 0
0x180012afa  jz      short loc_180012B1B
0x180012afc  lea     rcx, [rsp+48h+arg_8]; int *
0x180012b01  mov     [rsp+48h+arg_8], 0
0x180012b09  call    ?IsNetworkInitialized@@YAJPEAH@Z; IsNetworkInitialized(int *)
0x180012b0e  mov     ebx, eax
0x180012b10  test    eax, eax
0x180012b12  js      short loc_180012B20
0x180012b14  cmp     [rsp+48h+arg_8], 0
0x180012b19  jz      short loc_180012B20
0x180012b1b  mov     esi, 1
0x180012b20  mov     rcx, [rdi+0B0h]; hHandle
0x180012b27  mov     edx, 3E8h; dwMilliseconds
0x180012b2c  call    cs:__imp_WaitForSingleObject
0x180012b32  test    eax, eax
0x180012b34  jz      short loc_180012B3A
0x180012b36  test    esi, esi
0x180012b38  jz      short loc_180012ADD
0x180012b3a  test    ebx, ebx
0x180012b3c  js      short loc_180012B55
0x180012b3e  test    esi, esi
0x180012b40  jz      short loc_180012B55
0x180012b42  mov     rcx, [rsp+48h+arg_10]
0x180012b47  mov     rax, [rcx]
0x180012b4a  mov     rax, [rax+20h]
0x180012b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b53  mov     ebx, eax
0x180012b55  mov     rcx, [rsp+48h+arg_10]
0x180012b5a  mov     rax, [rcx]
0x180012b5d  mov     rax, [rax+10h]
0x180012b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b66  mov     rcx, [rdi+0B0h]; hObject
0x180012b6d  call    cs:__imp_CloseHandle
0x180012b73  mov     qword ptr [rdi+0B0h], 0
0x180012b7e  mov     rax, [rdi]
0x180012b81  mov     rcx, rdi
0x180012b84  mov     rax, [rax+10h]
0x180012b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b8d  call    cs:__imp_CoUninitialize
0x180012b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b9a  cmp     rcx, r15
0x180012b9d  jz      short loc_180012BBD
0x180012b9f  test    byte ptr [rcx+1Ch], 20h
0x180012ba3  jz      short loc_180012BBD
0x180012ba5  mov     rcx, [rcx+10h]
0x180012ba9  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180012bb0  mov     edx, 5Bh ; '['
0x180012bb5  mov     r9d, ebx
0x180012bb8  call    WPP_SF_d
0x180012bbd  mov     rbx, [rsp+48h+arg_0]
0x180012bc2  xor     eax, eax
0x180012bc4  add     rsp, 30h
0x180012bc8  pop     r15
0x180012bca  pop     rdi
0x180012bcb  pop     rsi
0x180012bcc  retn
```
