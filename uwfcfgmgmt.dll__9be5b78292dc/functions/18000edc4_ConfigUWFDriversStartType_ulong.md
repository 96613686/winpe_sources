# ConfigUWFDriversStartType(ulong)

- ea: `0x18000edc4`
- end: `0x18000ee42`
- name: `?ConfigUWFDriversStartType@@YAJK@Z`
- size: `126`
- prototype: `__int64 __fastcall(DWORD dwStartType)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000f258`

## callees

- `0x18000edc4`
- `0x18000fac0`
- `0x180011040`

## pseudocode

```c
__int64 __fastcall ConfigUWFDriversStartType(DWORD dwStartType)
{
  __int64 v2; // rbx
  const WCHAR *v3; // rsi
  __int64 result; // rax
  LPCWSTR lpServiceName[5]; // [rsp+20h] [rbp-28h]
  unsigned int v6; // [rsp+58h] [rbp+10h] BYREF

  lpServiceName[0] = L"uwfvol";
  v2 = 0;
  lpServiceName[1] = L"uwfs";
  lpServiceName[2] = L"uwfreg";
  do
  {
    v3 = lpServiceName[v2];
    v6 = 0;
    result = GetServiceStartType(v3, &v6);
    if ( (int)result < 0 )
      break;
    if ( v6 != dwStartType )
    {
      result = SetServiceStartType(v3, dwStartType);
      if ( (int)result < 0 )
        break;
    }
    v2 = (unsigned int)(v2 + 1);
  }
  while ( (unsigned int)v2 < 3 );
  return result;
}

```

## disassembly

```asm
0x18000edc4  mov     r11, rsp
0x18000edc7  mov     [r11+8], rbx
0x18000edcb  mov     [r11+18h], rsi
0x18000edcf  push    rdi
0x18000edd0  sub     rsp, 40h
0x18000edd4  lea     rax, aUwfvol_0; "uwfvol"
0x18000eddb  mov     edi, ecx
0x18000eddd  mov     [r11-28h], rax
0x18000ede1  xor     ebx, ebx
0x18000ede3  lea     rax, aUwfs; "uwfs"
0x18000edea  mov     [r11-20h], rax
0x18000edee  lea     rax, aUwfreg; "uwfreg"
0x18000edf5  mov     [r11-18h], rax
0x18000edf9  mov     rsi, [rsp+rbx*8+48h+lpServiceName]
0x18000edfe  lea     rdx, [rsp+48h+arg_8]; unsigned int *
0x18000ee03  mov     rcx, rsi; lpServiceName
0x18000ee06  mov     [rsp+48h+arg_8], 0
0x18000ee0e  call    ?GetServiceStartType@@YAJPEBGPEAK@Z; GetServiceStartType(ushort const *,ulong *)
0x18000ee13  test    eax, eax
0x18000ee15  js      short loc_18000EE32
0x18000ee17  cmp     [rsp+48h+arg_8], edi
0x18000ee1b  jz      short loc_18000EE2B
0x18000ee1d  mov     edx, edi; dwStartType
0x18000ee1f  mov     rcx, rsi; lpServiceName
0x18000ee22  call    ?SetServiceStartType@@YAJPEBGK@Z; SetServiceStartType(ushort const *,ulong)
0x18000ee27  test    eax, eax
0x18000ee29  js      short loc_18000EE32
0x18000ee2b  inc     ebx
0x18000ee2d  cmp     ebx, 3
0x18000ee30  jb      short loc_18000EDF9
0x18000ee32  mov     rbx, [rsp+48h+arg_0]
0x18000ee37  mov     rsi, [rsp+48h+arg_10]
0x18000ee3c  add     rsp, 40h
0x18000ee40  pop     rdi
0x18000ee41  retn
```
