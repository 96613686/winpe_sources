# SystemSettings::SetAdditionalAnimationSetting(uint)

- ea: `0x140018fd4`
- end: `0x140019089`
- name: `?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z`
- size: `181`
- prototype: `__int64 __fastcall(PVOID pvParam)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400191d0`

## callees

- `0x140018fd4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019036`
- `KERNEL32!GetLastError` at `0x140019036`
- `USER32!SystemParametersInfoW` at `0x140019022`
- `USER32!SystemParametersInfoW` at `0x140019066`
- `USER32!SystemParametersInfoW` at `0x140019022`
- `USER32!SystemParametersInfoW` at `0x140019066`

## pseudocode

```c
signed int __fastcall SystemSettings::SetAdditionalAnimationSetting(PVOID pvParam)
{
  unsigned __int64 v1; // rdi
  unsigned int v2; // ebx
  signed int result; // eax
  UINT uiAction[10]; // [rsp+20h] [rbp-28h]
  int pvParama; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v1 = (unsigned int)pvParam;
  v2 = 0;
  uiAction[0] = 4099;
  uiAction[1] = 4101;
  uiAction[2] = 4103;
  uiAction[3] = 4117;
  uiAction[4] = 4119;
  while ( v2 < 5 )
  {
    if ( !SystemParametersInfoW(uiAction[v2], 0, (PVOID)v1, 3u) )
      goto LABEL_5;
    ++v2;
  }
  pvParama = 8;
  v6 = v1;
  if ( SystemParametersInfoW(0x49u, 0, &pvParama, 3u) )
    return 0;
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140018fd4  mov     rax, rsp
0x140018fd7  mov     [rax+8], rbx
0x140018fdb  mov     [rax+18h], rsi
0x140018fdf  push    rdi
0x140018fe0  sub     rsp, 40h
0x140018fe4  mov     edi, ecx
0x140018fe6  xor     ebx, ebx
0x140018fe8  mov     dword ptr [rax-28h], 1003h
0x140018fef  mov     dword ptr [rax-24h], 1005h
0x140018ff6  mov     dword ptr [rax-20h], 1007h
0x140018ffd  mov     dword ptr [rax-1Ch], 1015h
0x140019004  mov     dword ptr [rax-18h], 1017h
0x14001900b  xor     edx, edx; uiParam
0x14001900d  mov     r9d, 3; fWinIni
0x140019013  cmp     ebx, 5
0x140019016  jnb     short loc_140019050
0x140019018  movsxd  rcx, ebx
0x14001901b  mov     r8, rdi; pvParam
0x14001901e  mov     ecx, [rsp+rcx*4+48h+uiAction]; uiAction
0x140019022  call    cs:__imp_SystemParametersInfoW
0x140019029  nop     dword ptr [rax+rax+00h]
0x14001902e  test    eax, eax
0x140019030  jz      short loc_140019036
0x140019032  inc     ebx
0x140019034  jmp     short loc_14001900B
0x140019036  call    cs:__imp_GetLastError
0x14001903d  nop     dword ptr [rax+rax+00h]
0x140019042  test    eax, eax
0x140019044  jle     short loc_140019078
0x140019046  movzx   eax, ax
0x140019049  or      eax, 80070000h
0x14001904e  jmp     short loc_140019078
0x140019050  lea     r8, [rsp+48h+pvParam]; pvParam
0x140019055  mov     [rsp+48h+pvParam], 8
0x14001905d  mov     ecx, 49h ; 'I'; uiAction
0x140019062  mov     [rsp+48h+arg_C], edi
0x140019066  call    cs:__imp_SystemParametersInfoW
0x14001906d  nop     dword ptr [rax+rax+00h]
0x140019072  test    eax, eax
0x140019074  jz      short loc_140019036
0x140019076  xor     eax, eax
0x140019078  mov     rbx, [rsp+48h+arg_0]
0x14001907d  mov     rsi, [rsp+48h+arg_10]
0x140019082  add     rsp, 40h
0x140019086  pop     rdi
0x140019087  retn
```
