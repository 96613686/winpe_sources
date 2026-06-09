# StorageReady::_ProcessNewDisk(ushort const *)

- ea: `0x1800197a4`
- end: `0x1800199a0`
- name: `?_ProcessNewDisk@StorageReady@@YAJPEBG@Z`
- size: `508`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, __int64, struct CSafeHandle **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180019760`

## callees

- `0x180003570`
- `0x1800046c0`
- `0x1800147f0`
- `0x180018db4`
- `0x180019028`
- `0x1800197a4`
- `0x18001b404`
- `0x18002b8cc`
- `0x18002e738`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800198b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800198b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019804`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019875`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019841`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019841`

## pseudocode

```c
__int64 __fastcall StorageReady::_ProcessNewDisk(
        const WCHAR *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct CSafeHandle **a4)
{
  int DeviceHandleSafe; // ebx
  struct Autoplay::IDeviceProperties *v6; // r15
  int v7; // edi
  int v8; // r12d
  DWORD nOutBufferSize; // r14d
  HANDLE ProcessHeap; // rax
  unsigned int *lpOutBuffer; // rsi
  unsigned int i; // eax
  __int64 v13; // rcx
  DWORD LastError; // eax
  HANDLE v15; // rax
  unsigned int v16; // edx
  struct Autoplay::IDeviceProperties **v17; // r8
  Autoplay *v18; // rax
  struct Autoplay::IDeviceProperties *v19; // rsi
  Autoplay *v20; // rdi
  struct Autoplay::CDispatchDeviceEvent *v21; // rdx
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF
  struct Autoplay::IDeviceProperties *v24; // [rsp+80h] [rbp+18h] BYREF

  v24 = 0;
  DeviceHandleSafe = PnPHelper::GetDeviceHandleSafe(this, (const unsigned __int16 *)1, &v24, a4);
  if ( DeviceHandleSafe >= 0 )
  {
    v6 = v24;
    v7 = 0;
    v8 = 0;
    BytesReturned = 0;
    nOutBufferSize = 72;
    do
    {
      ProcessHeap = GetProcessHeap();
      lpOutBuffer = (unsigned int *)HeapAlloc(ProcessHeap, 8u, nOutBufferSize);
      if ( lpOutBuffer )
      {
        if ( DeviceIoControl(*(HANDLE *)v6, 0x7400Cu, 0, 0, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
        {
          for ( i = 0; i < *lpOutBuffer; ++i )
          {
            v13 = 8LL * i;
            if ( BYTE2(lpOutBuffer[v13 + 8]) || LOBYTE(lpOutBuffer[v13 + 8]) )
            {
              v8 = 1;
              break;
            }
          }
          DeviceHandleSafe = 0;
          v7 = 0;
        }
        else
        {
          LastError = GetLastError();
          v7 = 0;
          if ( (LastError == 122 || LastError == 234 || LastError == 24) && nOutBufferSize < 0x4000 )
          {
            nOutBufferSize *= 2;
            v7 = 1;
          }
          DeviceHandleSafe = -2147467259;
        }
        v15 = GetProcessHeap();
        HeapFree(v15, 0, lpOutBuffer);
      }
      else
      {
        DeviceHandleSafe = -2147024882;
      }
    }
    while ( v7 );
    CSafeHandle::_CloseAll(v6);
    if ( v6 )
      CSafeHandle::`scalar deleting destructor'(v6, v16);
    if ( DeviceHandleSafe >= 0 && !v8 )
    {
      v24 = 0;
      DeviceHandleSafe = StorageReady::_GetDevicePropertiesObject(this, (struct CRefCounted *)&v24, v17);
      if ( DeviceHandleSafe >= 0 )
      {
        v18 = (Autoplay *)operator new(0x2B8u);
        v19 = v24;
        v20 = v18;
        if ( v18 )
        {
          *((_DWORD *)v18 + 2) = 1;
          *((_QWORD *)v18 + 85) = 0;
          *(_QWORD *)v18 = &Autoplay::CDispatchDeviceEvent::`vftable';
          DeviceHandleSafe = Autoplay::CDispatchDeviceEvent::Init(v18, 0, this, L"DeviceArrival", v19);
          if ( DeviceHandleSafe >= 0 )
            DeviceHandleSafe = Autoplay::DispatchDeviceEvent(v20, v21);
          CRefCounted::Release(v20);
        }
        else
        {
          DeviceHandleSafe = -2147024882;
        }
        CRefCounted::Release(v19);
      }
    }
  }
  return (unsigned int)DeviceHandleSafe;
}

```

## disassembly

```asm
0x1800197a4  mov     rax, rsp
0x1800197a7  mov     [rax+8], rbx
0x1800197ab  mov     [rax+20h], rbp
0x1800197af  push    rsi
0x1800197b0  push    rdi
0x1800197b1  push    r12
0x1800197b3  push    r14
0x1800197b5  push    r15
0x1800197b7  sub     rsp, 40h
0x1800197bb  lea     r8, [rax+18h]; int
0x1800197bf  mov     qword ptr [rax+18h], 0
0x1800197c7  mov     edx, 1; unsigned __int16 *
0x1800197cc  mov     rbp, rcx
0x1800197cf  call    ?GetDeviceHandleSafe@PnPHelper@@YAJPEBGHPEAPEAVCSafeHandle@@@Z; PnPHelper::GetDeviceHandleSafe(ushort const *,int,CSafeHandle * *)
0x1800197d4  mov     ebx, eax
0x1800197d6  test    eax, eax
0x1800197d8  js      loc_180019985
0x1800197de  mov     r15, [rsp+68h+arg_10]
0x1800197e6  xor     edi, edi
0x1800197e8  xor     r12d, r12d
0x1800197eb  mov     [rsp+68h+BytesReturned], edi
0x1800197ef  lea     r14d, [rdi+48h]
0x1800197f3  call    cs:__imp_GetProcessHeap
0x1800197f9  mov     r8d, r14d; dwBytes
0x1800197fc  mov     edx, 8; dwFlags
0x180019801  mov     rcx, rax; hHeap
0x180019804  call    cs:__imp_HeapAlloc
0x18001980a  mov     rsi, rax
0x18001980d  test    rax, rax
0x180019810  jz      loc_1800198BA
0x180019816  mov     rcx, [r15]; hDevice
0x180019819  lea     rax, [rsp+68h+BytesReturned]
0x18001981e  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180019827  xor     r9d, r9d; nInBufferSize
0x18001982a  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18001982f  xor     r8d, r8d; lpInBuffer
0x180019832  mov     [rsp+68h+nOutBufferSize], r14d; nOutBufferSize
0x180019837  mov     edx, 7400Ch; dwIoControlCode
0x18001983c  mov     [rsp+68h+lpOutBuffer], rsi; lpOutBuffer
0x180019841  call    cs:__imp_DeviceIoControl
0x180019847  test    eax, eax
0x180019849  jz      short loc_180019875
0x18001984b  xor     eax, eax
0x18001984d  cmp     eax, [rsi]
0x18001984f  jnb     short loc_18001986F
0x180019851  mov     ecx, eax
0x180019853  shl     rcx, 5
0x180019857  cmp     byte ptr [rcx+rsi+22h], 0
0x18001985c  jnz     short loc_180019869
0x18001985e  cmp     byte ptr [rcx+rsi+20h], 0
0x180019863  jnz     short loc_180019869
0x180019865  inc     eax
0x180019867  jmp     short loc_18001984D
0x180019869  mov     r12d, 1
0x18001986f  xor     ebx, ebx
0x180019871  xor     edi, edi
0x180019873  jmp     short loc_1800198A4
0x180019875  call    cs:__imp_GetLastError
0x18001987b  xor     edi, edi
0x18001987d  cmp     eax, 7Ah ; 'z'
0x180019880  jz      short loc_18001988E
0x180019882  cmp     eax, 0EAh
0x180019887  jz      short loc_18001988E
0x180019889  cmp     eax, 18h
0x18001988c  jnz     short loc_18001989F
0x18001988e  cmp     r14d, 4000h
0x180019895  jnb     short loc_18001989F
0x180019897  add     r14d, r14d
0x18001989a  mov     edi, 1
0x18001989f  mov     ebx, 80004005h
0x1800198a4  call    cs:__imp_GetProcessHeap
0x1800198aa  mov     r8, rsi; lpMem
0x1800198ad  xor     edx, edx; dwFlags
0x1800198af  mov     rcx, rax; hHeap
0x1800198b2  call    cs:__imp_HeapFree
0x1800198b8  jmp     short loc_1800198BF
0x1800198ba  mov     ebx, 8007000Eh
0x1800198bf  test    edi, edi
0x1800198c1  jnz     loc_1800197F3
0x1800198c7  mov     rcx, r15; this
0x1800198ca  call    ?_CloseAll@CSafeHandle@@AEAAJXZ; CSafeHandle::_CloseAll(void)
0x1800198cf  test    r15, r15
0x1800198d2  jz      short loc_1800198DC
0x1800198d4  mov     rcx, r15; this
0x1800198d7  call    ??_GCSafeHandle@@QEAAPEAXI@Z; CSafeHandle::`scalar deleting destructor'(uint)
0x1800198dc  test    ebx, ebx
0x1800198de  js      loc_180019985
0x1800198e4  test    r12d, r12d
0x1800198e7  jnz     loc_180019985
0x1800198ed  lea     rdx, [rsp+68h+arg_10]; unsigned __int16 *
0x1800198f5  mov     [rsp+68h+arg_10], 0
0x180019901  mov     rcx, rbp; this
0x180019904  call    ?_GetDevicePropertiesObject@StorageReady@@YAJPEBGPEAPEAVIDeviceProperties@Autoplay@@@Z; StorageReady::_GetDevicePropertiesObject(ushort const *,Autoplay::IDeviceProperties * *)
0x180019909  mov     ebx, eax
0x18001990b  test    eax, eax
0x18001990d  js      short loc_180019985
0x18001990f  mov     ecx, 2B8h; Size
0x180019914  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019919  mov     rsi, [rsp+68h+arg_10]
0x180019921  mov     rdi, rax
0x180019924  test    rax, rax
0x180019927  jz      short loc_180019978
0x180019929  mov     dword ptr [rax+8], 1
0x180019930  lea     r9, aDevicearrival; "DeviceArrival"
0x180019937  lea     rax, ??_7CDispatchDeviceEvent@Autoplay@@6B@; const Autoplay::CDispatchDeviceEvent::`vftable'
0x18001993e  mov     qword ptr [rdi+2A8h], 0
0x180019949  mov     r8, rbp; unsigned __int16 *
0x18001994c  mov     [rdi], rax
0x18001994f  xor     edx, edx; struct _GUID *
0x180019951  mov     [rsp+68h+lpOutBuffer], rsi; struct Autoplay::IDeviceProperties *
0x180019956  mov     rcx, rdi; this
0x180019959  call    ?Init@CDispatchDeviceEvent@Autoplay@@QEAAJPEBU_GUID@@PEBG1PEAVIDeviceProperties@2@H@Z; Autoplay::CDispatchDeviceEvent::Init(_GUID const *,ushort const *,ushort const *,Autoplay::IDeviceProperties *,int)
0x18001995e  mov     ebx, eax
0x180019960  test    eax, eax
0x180019962  js      short loc_18001996E
0x180019964  mov     rcx, rdi; this
0x180019967  call    ?DispatchDeviceEvent@Autoplay@@YAJPEAVCDispatchDeviceEvent@1@@Z; Autoplay::DispatchDeviceEvent(Autoplay::CDispatchDeviceEvent *)
0x18001996c  mov     ebx, eax
0x18001996e  mov     rcx, rdi; this
0x180019971  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180019976  jmp     short loc_18001997D
0x180019978  mov     ebx, 8007000Eh
0x18001997d  mov     rcx, rsi; this
0x180019980  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180019985  lea     r11, [rsp+68h+var_28]
0x18001998a  mov     eax, ebx
0x18001998c  mov     rbx, [r11+30h]
0x180019990  mov     rbp, [r11+48h]
0x180019994  mov     rsp, r11
0x180019997  pop     r15
0x180019999  pop     r14
0x18001999b  pop     r12
0x18001999d  pop     rdi
0x18001999e  pop     rsi
0x18001999f  retn
```
