# UmpoInternalClearPowerSubkeyCache

- ea: `0x18000e030`
- end: `0x18000e0b3`
- name: `UmpoInternalClearPowerSubkeyCache`
- size: `131`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f4c`
- `0x180013808`

## callees

- `0x18000e030`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e04b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e04b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e070`

## pseudocode

```c
void __fastcall UmpoInternalClearPowerSubkeyCache(__int64 a1)
{
  __int64 i; // rbp
  __int64 v3; // rdi
  HKEY v4; // rcx

  if ( *(_BYTE *)(a1 + 112) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  for ( i = 0; i != 2; ++i )
  {
    v3 = 32 * i;
    if ( !*(_DWORD *)(32 * i + a1 + 32) )
    {
      v4 = *(HKEY *)(v3 + a1 + 24);
      if ( (unsigned __int64)v4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(v4);
        *(_QWORD *)(v3 + a1 + 24) = -1;
      }
    }
    *(GUID *)(v3 + a1 + 8) = GUID_NULL;
  }
  if ( *(_BYTE *)(a1 + 112) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
}

```

## disassembly

```asm
0x18000e030  push    rbx
0x18000e032  push    rbp
0x18000e033  push    rsi
0x18000e034  push    rdi
0x18000e035  sub     rsp, 28h
0x18000e039  cmp     byte ptr [rcx+70h], 1
0x18000e03d  mov     rsi, rcx
0x18000e040  jz      short loc_18000E047
0x18000e042  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e047  lea     rcx, [rsi+48h]; lpCriticalSection
0x18000e04b  call    cs:__imp_EnterCriticalSection
0x18000e051  xor     ebp, ebp
0x18000e053  mov     rdi, rbp
0x18000e056  shl     rdi, 5
0x18000e05a  cmp     dword ptr [rdi+rsi+20h], 0
0x18000e05f  jnz     short loc_18000E07F
0x18000e061  mov     rcx, [rdi+rsi+18h]; hKey
0x18000e066  lea     rax, [rcx-1]
0x18000e06a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e06e  ja      short loc_18000E07F
0x18000e070  call    cs:__imp_RegCloseKey
0x18000e076  mov     qword ptr [rdi+rsi+18h], 0FFFFFFFFFFFFFFFFh
0x18000e07f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e086  inc     rbp
0x18000e089  movdqu  xmmword ptr [rdi+rsi+8], xmm0
0x18000e08f  cmp     rbp, 2
0x18000e093  jnz     short loc_18000E053
0x18000e095  cmp     byte ptr [rsi+70h], 1
0x18000e099  jz      short loc_18000E0A0
0x18000e09b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e0a0  lea     rcx, [rsi+48h]
0x18000e0a4  add     rsp, 28h
0x18000e0a8  pop     rdi
0x18000e0a9  pop     rsi
0x18000e0aa  pop     rbp
0x18000e0ab  pop     rbx
0x18000e0ac  jmp     cs:__imp_LeaveCriticalSection
```
