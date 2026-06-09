# CNewTimer::SaveToRegistry(void)

- ea: `0x180010144`
- end: `0x18001021a`
- name: `?SaveToRegistry@CNewTimer@@AEAAXXZ`
- size: `214`
- prototype: `void __fastcall(CNewTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180010220`

## callees

- `0x18001011c`
- `0x180010144`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010172`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011cd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011cd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001019a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001019a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800101ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800101ee`

## string_xrefs

- `0x18001018c`: `System\CurrentControlSet\Services\TrkWks\Parameters`

## pseudocode

```c
void __fastcall CNewTimer::SaveToRegistry(CNewTimer *this)
{
  LSTATUS v2; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v4; // [rsp+38h] [rbp-20h]
  int v5; // [rsp+40h] [rbp-18h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  if ( *((_QWORD *)this + 8) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\TrkWks\\Parameters",
           0,
           0x2000000u,
           &hKey);
    CNewTimer::PersistentState::PersistentState((CNewTimer::PersistentState *)Data);
    *(_QWORD *)Data = *((_QWORD *)this + 16);
    v4 = *((_QWORD *)this + 15);
    v5 = *((_DWORD *)this + 29);
    if ( !v2 )
    {
      RegSetValueExW(hKey, *((LPCWSTR *)this + 8), 0, 3u, Data, 0x18u);
      RegCloseKey(hKey);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180010144  mov     rax, rsp
0x180010147  mov     [rax+18h], rbx
0x18001014b  mov     [rax+20h], rsi
0x18001014f  mov     [rax+8], rcx
0x180010153  push    rdi
0x180010154  sub     rsp, 50h
0x180010158  mov     rdi, rcx
0x18001015b  mov     qword ptr [rax+10h], 0
0x180010163  cmp     qword ptr [rcx+40h], 0
0x180010168  jz      loc_18001020A
0x18001016e  add     rcx, 10h; lpCriticalSection
0x180010172  call    cs:__imp_EnterCriticalSection
0x180010178  nop
0x180010179  lea     rax, [rsp+58h+hKey]
0x18001017e  mov     [rsp+58h+phkResult], rax; phkResult
0x180010183  mov     r9d, 2000000h; samDesired
0x180010189  xor     r8d, r8d; ulOptions
0x18001018c  lea     rdx, ?s_tszKeyNameLinkTrack@@3QBGB; "System\\CurrentControlSet\\Services\\Tr"...
0x180010193  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001019a  call    cs:__imp_RegOpenKeyExW
0x1800101a0  mov     ebx, eax
0x1800101a2  lea     rcx, [rsp+58h+Data]; this
0x1800101a7  call    ??0PersistentState@CNewTimer@@QEAA@XZ; CNewTimer::PersistentState::PersistentState(void)
0x1800101ac  mov     rcx, [rdi+80h]
0x1800101b3  mov     qword ptr [rsp+58h+Data], rcx
0x1800101b8  mov     rcx, [rdi+78h]
0x1800101bc  mov     [rsp+58h+var_20], rcx
0x1800101c1  mov     ecx, [rdi+74h]
0x1800101c4  mov     [rsp+58h+var_18], ecx
0x1800101c8  test    ebx, ebx
0x1800101ca  jnz     short loc_180010200
0x1800101cc  mov     [rsp+58h+cbData], 18h; cbData
0x1800101d4  lea     rax, [rsp+58h+Data]
0x1800101d9  mov     [rsp+58h+phkResult], rax; lpData
0x1800101de  lea     r9d, [rbx+3]; dwType
0x1800101e2  xor     r8d, r8d; Reserved
0x1800101e5  mov     rdx, [rdi+40h]; lpValueName
0x1800101e9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800101ee  call    cs:__imp_RegSetValueExW
0x1800101f4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800101f9  call    cs:__imp_RegCloseKey
0x1800101ff  nop
0x180010200  lea     rcx, [rdi+10h]; lpCriticalSection
0x180010204  call    cs:__imp_LeaveCriticalSection
0x18001020a  mov     rbx, [rsp+58h+arg_10]
0x18001020f  mov     rsi, [rsp+58h+arg_18]
0x180010214  add     rsp, 50h
0x180010218  pop     rdi
0x180010219  retn
0x180011cc3  push    rbp
0x180011cc5  sub     rsp, 30h
0x180011cc9  mov     rbp, rdx
0x180011ccc  mov     rcx, [rbp+60h]
0x180011cd0  add     rcx, 10h; lpCriticalSection
0x180011cd4  call    cs:__imp_LeaveCriticalSection
0x180011cda  nop
0x180011cdb  add     rsp, 30h
0x180011cdf  pop     rbp
0x180011ce0  retn
```
