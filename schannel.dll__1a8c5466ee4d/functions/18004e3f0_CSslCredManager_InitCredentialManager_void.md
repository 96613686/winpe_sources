# CSslCredManager::InitCredentialManager(void)

- ea: `0x18004e3f0`
- end: `0x18004e49f`
- name: `?InitCredentialManager@CSslCredManager@@QEAAEXZ`
- size: `175`
- prototype: `unsigned __int8 __fastcall(CSslCredManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180025c38`

## callees

- `0x18004e3f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004e423`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004e475`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004e423`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004e475`
- `ntdll!RtlInitializeCriticalSection` at `0x18004e3fd`
- `ntdll!RtlInitializeCriticalSection` at `0x18004e3fd`
- `CRYPT32!CertOpenStore` at `0x18004e45c`
- `CRYPT32!CertOpenStore` at `0x18004e45c`
- `CRYPT32!CertControlStore` at `0x18004e491`
- `CRYPT32!CertControlStore` at `0x18004e491`
- `USERENV!RegisterGPNotification` at `0x18004e43a`
- `USERENV!RegisterGPNotification` at `0x18004e43a`

## pseudocode

```c
unsigned __int8 __fastcall CSslCredManager::InitCredentialManager(CSslCredManager *this)
{
  HANDLE EventA; // rax
  HCERTSTORE v4; // rax
  HANDLE v5; // rax

  if ( RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 8)) < 0 )
    return 0;
  *((_QWORD *)this + 7) = (char *)this + 48;
  *((_QWORD *)this + 6) = (char *)this + 48;
  EventA = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)this + 8) = EventA;
  if ( EventA )
    RegisterGPNotification(EventA, 1);
  v4 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20020000u, L"MY");
  *((_QWORD *)this + 9) = v4;
  if ( v4 )
  {
    v5 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 10) = v5;
    if ( v5 )
      CertControlStore(*((HCERTSTORE *)this + 9), 0, 2u, (char *)this + 80);
  }
  return 1;
}

```

## disassembly

```asm
0x18004e3f0  push    rbx
0x18004e3f2  sub     rsp, 30h
0x18004e3f6  mov     rbx, rcx
0x18004e3f9  add     rcx, 8; CriticalSection
0x18004e3fd  call    cs:__imp_RtlInitializeCriticalSection
0x18004e403  test    eax, eax
0x18004e405  jns     short loc_18004E40E
0x18004e407  xor     al, al
0x18004e409  jmp     loc_18004E499
0x18004e40e  lea     rax, [rbx+30h]
0x18004e412  xor     r9d, r9d; lpName
0x18004e415  xor     r8d, r8d; bInitialState
0x18004e418  mov     [rax+8], rax
0x18004e41c  xor     edx, edx; bManualReset
0x18004e41e  mov     [rax], rax
0x18004e421  xor     ecx, ecx; lpEventAttributes
0x18004e423  call    cs:__imp_CreateEventA
0x18004e429  mov     [rbx+40h], rax
0x18004e42d  test    rax, rax
0x18004e430  jz      short loc_18004E440
0x18004e432  mov     edx, 1; bMachine
0x18004e437  mov     rcx, rax; hEvent
0x18004e43a  call    cs:__imp_RegisterGPNotification
0x18004e440  xor     r8d, r8d; hCryptProv
0x18004e443  lea     rax, aMy; "MY"
0x18004e44a  mov     r9d, 20020000h; dwFlags
0x18004e450  mov     [rsp+38h+pvPara], rax; pvPara
0x18004e455  lea     edx, [r8+1]; dwEncodingType
0x18004e459  lea     ecx, [rdx+9]; lpszStoreProvider
0x18004e45c  call    cs:__imp_CertOpenStore
0x18004e462  mov     [rbx+48h], rax
0x18004e466  test    rax, rax
0x18004e469  jz      short loc_18004E497
0x18004e46b  xor     r9d, r9d; lpName
0x18004e46e  xor     r8d, r8d; bInitialState
0x18004e471  xor     edx, edx; bManualReset
0x18004e473  xor     ecx, ecx; lpEventAttributes
0x18004e475  call    cs:__imp_CreateEventA
0x18004e47b  lea     r9, [rbx+50h]; pvCtrlPara
0x18004e47f  mov     [r9], rax
0x18004e482  test    rax, rax
0x18004e485  jz      short loc_18004E497
0x18004e487  mov     rcx, [rbx+48h]; hCertStore
0x18004e48b  xor     edx, edx; dwFlags
0x18004e48d  lea     r8d, [rdx+2]; dwCtrlType
0x18004e491  call    cs:__imp_CertControlStore
0x18004e497  mov     al, 1
0x18004e499  add     rsp, 30h
0x18004e49d  pop     rbx
0x18004e49e  retn
```
