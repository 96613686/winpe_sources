# CaptureUwfSettings(E_UNATTEND_REASON)

- ea: `0x18000e780`
- end: `0x18000e87e`
- name: `?CaptureUwfSettings@@YAJW4E_UNATTEND_REASON@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000f258`

## callees

- `0x18000d5f0`
- `0x18000d630`
- `0x18000d9f0`
- `0x18000de30`
- `0x18000e480`
- `0x18000e780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000e844`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000e844`

## string_xrefs

- `0x18000e7a6`: `SYSTEM\CurrentControlSet\Services\UWFVOL`

## pseudocode

```c
__int64 __fastcall CaptureUwfSettings(int a1)
{
  signed int v2; // ebx
  LSTATUS v3; // eax
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( (int)CUwfRegKey::Open(&hKey, HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL", 0xF003Fu) < 0
    || (int)CUwfRegKey::Create(&phkResult, hKey, L"Parameters.Default", 0, 0, 0xF003Fu, 0, 0) < 0
    || (v2 = CUwfRegKey::CopyTree((CUwfRegKey *)&hKey, phkResult, L"Parameters", 1), v2 < 0) )
  {
    v2 = 0;
    v3 = RegDeleteTreeW(hKey, L"Parameters.Default");
    if ( v3 )
    {
      if ( v3 > 0 )
      {
        v2 = (unsigned __int16)v3 | 0x80070000;
        goto LABEL_10;
      }
      goto LABEL_8;
    }
  }
  else if ( !a1 )
  {
    v3 = CUwfRegKey::SetDWORDValue((CUwfRegKey *)&phkResult, L"CapturedUwfSettings", 1u);
LABEL_8:
    v2 = v3;
  }
LABEL_10:
  CUwfRegKey::Close((CUwfRegKey *)&phkResult);
  CUwfRegKey::Close((CUwfRegKey *)&hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000e780  mov     rax, rsp
0x18000e783  mov     [rax+8], rbx
0x18000e787  push    rdi
0x18000e788  sub     rsp, 40h
0x18000e78c  mov     edi, ecx
0x18000e78e  mov     qword ptr [rax+10h], 0
0x18000e796  mov     ebx, 0F003Fh
0x18000e79b  mov     qword ptr [rax+18h], 0
0x18000e7a3  mov     r9d, ebx; samDesired
0x18000e7a6  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x18000e7ad  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000e7b4  lea     rcx, [rax+10h]; phkResult
0x18000e7b8  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000e7bd  test    eax, eax
0x18000e7bf  js      short loc_18000E836
0x18000e7c1  mov     rdx, [rsp+48h+hKey]; hKey
0x18000e7c6  lea     r8, SubKey; "Parameters.Default"
0x18000e7cd  mov     [rsp+48h+var_10], 0; LPDWORD
0x18000e7d6  lea     rcx, [rsp+48h+phkResult]; phkResult
0x18000e7db  mov     [rsp+48h+var_18], 0; LPSECURITY_ATTRIBUTES
0x18000e7e4  xor     r9d, r9d; lpClass
0x18000e7e7  mov     [rsp+48h+var_20], ebx; REGSAM
0x18000e7eb  mov     [rsp+48h+var_28], 0; DWORD
0x18000e7f3  call    ?Create@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CUwfRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000e7f8  test    eax, eax
0x18000e7fa  js      short loc_18000E836
0x18000e7fc  mov     rdx, [rsp+48h+phkResult]; HKEY
0x18000e801  lea     r8, aParameters; "Parameters"
0x18000e808  mov     r9b, 1; bool
0x18000e80b  lea     rcx, [rsp+48h+hKey]; this
0x18000e810  call    ?CopyTree@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBG_N@Z; CUwfRegKey::CopyTree(HKEY__ *,ushort const *,bool)
0x18000e815  mov     ebx, eax
0x18000e817  test    eax, eax
0x18000e819  js      short loc_18000E836
0x18000e81b  test    edi, edi
0x18000e81d  jnz     short loc_18000E85D
0x18000e81f  lea     r8d, [rdi+1]; unsigned int
0x18000e823  lea     rdx, aCaptureduwfset; "CapturedUwfSettings"
0x18000e82a  lea     rcx, [rsp+48h+phkResult]; this
0x18000e82f  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x18000e834  jmp     short loc_18000E850
0x18000e836  mov     rcx, [rsp+48h+hKey]; hKey
0x18000e83b  lea     rdx, SubKey; "Parameters.Default"
0x18000e842  xor     ebx, ebx
0x18000e844  call    cs:__imp_RegDeleteTreeW
0x18000e84a  test    eax, eax
0x18000e84c  jz      short loc_18000E85D
0x18000e84e  jg      short loc_18000E854
0x18000e850  mov     ebx, eax
0x18000e852  jmp     short loc_18000E85D
0x18000e854  movzx   ebx, ax
0x18000e857  or      ebx, 80070000h
0x18000e85d  lea     rcx, [rsp+48h+phkResult]; this
0x18000e862  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000e867  lea     rcx, [rsp+48h+hKey]; this
0x18000e86c  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000e871  mov     eax, ebx
0x18000e873  mov     rbx, [rsp+48h+arg_0]
0x18000e878  add     rsp, 40h
0x18000e87c  pop     rdi
0x18000e87d  retn
```
