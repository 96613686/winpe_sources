# AlternativePortSetRegistryEntry

- ea: `0x180020440`
- end: `0x180020690`
- name: `AlternativePortSetRegistryEntry`
- size: `592`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180020ae0`

## callees

- `0x18001deb0`
- `0x18001e8bc`
- `0x180020440`
- `0x180020de8`
- `0x180020f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002055d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002055d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800205d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800205d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020666`

## string_xrefs

- `0x180020530`: `SYSTEM\CurrentControlSet\Services\LanmanServer\AlternativePorts`

## pseudocode

```c
__int64 __fastcall AlternativePortSetRegistryEntry(unsigned __int16 *a1)
{
  unsigned int v1; // edi
  unsigned int v2; // ebx
  const wchar_t *v3; // r9
  unsigned __int16 v4; // si
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  BYTE Data[8]; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF
  WCHAR Buffer[12]; // [rsp+60h] [rbp-28h] BYREF

  v1 = *((unsigned __int8 *)a1 + 2);
  hKey = 0;
  memset(Buffer, 0, 22);
  *(_DWORD *)Data = *((_DWORD *)a1 + 1) & ~*((_DWORD *)a1 + 2);
  switch ( v1 )
  {
    case 1u:
      v3 = L"tcp";
      break;
    case 2u:
      v3 = L"rdma";
      break;
    case 4u:
      v3 = L"quic";
      break;
    default:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids, v1);
      }
      v2 = 50;
      goto LABEL_28;
  }
  v4 = *a1;
  v5 = swprintf_s(Buffer, 0xBu, L"%s:%lu", v3, *a1);
  if ( v5 - 1 > 0xFFFFFFFD )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids, v5);
    }
    v2 = 1359;
  }
  else
  {
    v2 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\AlternativePorts",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids, v2);
      }
    }
    else
    {
      v2 = RegSetValueExW(hKey, Buffer, 0, 4u, Data, 4u);
      if ( v2
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_HDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v4, v1, *(_DWORD *)Data, v2);
      }
    }
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180020440  mov     r11, rsp
0x180020443  mov     [r11+10h], rbx
0x180020447  mov     [r11+18h], rsi
0x18002044b  push    rdi
0x18002044c  sub     rsp, 80h
0x180020453  mov     rax, cs:__security_cookie
0x18002045a  xor     rax, rsp
0x18002045d  mov     [rsp+88h+var_10], rax
0x180020462  movzx   edi, byte ptr [rcx+2]
0x180020466  xor     eax, eax
0x180020468  mov     [r11-30h], rax
0x18002046c  mov     rdx, rcx
0x18002046f  xorps   xmm0, xmm0
0x180020472  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x180020477  mov     [r11-1Ah], rax
0x18002047b  mov     eax, [rcx+8]
0x18002047e  not     eax
0x180020480  and     eax, [rcx+4]
0x180020483  mov     ecx, edi
0x180020485  mov     dword ptr [rsp+88h+Data], eax
0x180020489  sub     ecx, 1
0x18002048c  jz      short loc_1800204EB
0x18002048e  sub     ecx, 1
0x180020491  jz      short loc_1800204E2
0x180020493  cmp     ecx, 2
0x180020496  jz      short loc_1800204D9
0x180020498  mov     rcx, cs:WPP_GLOBAL_Control
0x18002049f  lea     rax, WPP_GLOBAL_Control
0x1800204a6  cmp     rcx, rax
0x1800204a9  jz      short loc_1800204CF
0x1800204ab  test    byte ptr [rcx+1Ch], 1
0x1800204af  jz      short loc_1800204CF
0x1800204b1  cmp     byte ptr [rcx+19h], 1
0x1800204b5  jb      short loc_1800204CF
0x1800204b7  mov     rcx, [rcx+10h]
0x1800204bb  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x1800204c2  mov     edx, 0Ch
0x1800204c7  mov     r9d, edi
0x1800204ca  call    WPP_SF_d
0x1800204cf  mov     ebx, 32h ; '2'
0x1800204d4  jmp     loc_18002065C
0x1800204d9  lea     r9, aQuic; "quic"
0x1800204e0  jmp     short loc_1800204F2
0x1800204e2  lea     r9, aRdma; "rdma"
0x1800204e9  jmp     short loc_1800204F2
0x1800204eb  lea     r9, aTcp; "tcp"
0x1800204f2  movzx   esi, word ptr [rdx]
0x1800204f5  lea     r8, aSLu; "%s:%lu"
0x1800204fc  mov     edx, 0Bh; BufferCount
0x180020501  mov     [rsp+88h+dwOptions], esi
0x180020505  lea     rcx, [rsp+88h+Buffer]; Buffer
0x18002050a  call    swprintf_s
0x18002050f  mov     r9d, eax
0x180020512  dec     eax
0x180020514  cmp     eax, 0FFFFFFFDh
0x180020517  ja      loc_180020623
0x18002051d  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180020526  lea     rax, [rsp+88h+hKey]
0x18002052b  mov     [rsp+88h+phkResult], rax; phkResult
0x180020530  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x180020537  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180020540  xor     r9d, r9d; lpClass
0x180020543  mov     [rsp+88h+samDesired], 2; samDesired
0x18002054b  xor     r8d, r8d; Reserved
0x18002054e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020555  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18002055d  call    cs:__imp_RegCreateKeyExW
0x180020563  mov     ebx, eax
0x180020565  test    eax, eax
0x180020567  jz      short loc_1800205B4
0x180020569  mov     rcx, cs:WPP_GLOBAL_Control
0x180020570  lea     rax, WPP_GLOBAL_Control
0x180020577  cmp     rcx, rax
0x18002057a  jz      loc_18002065C
0x180020580  test    dword ptr [rcx+1Ch], 100h
0x180020587  jz      loc_18002065C
0x18002058d  cmp     byte ptr [rcx+19h], 1
0x180020591  jb      loc_18002065C
0x180020597  mov     rcx, [rcx+10h]
0x18002059b  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x1800205a2  mov     edx, 0Eh
0x1800205a7  mov     r9d, ebx
0x1800205aa  call    WPP_SF_d
0x1800205af  jmp     loc_18002065C
0x1800205b4  mov     rcx, [rsp+88h+hKey]; hKey
0x1800205b9  lea     rax, [rsp+88h+Data]
0x1800205be  mov     r9d, 4; dwType
0x1800205c4  lea     rdx, [rsp+88h+Buffer]; lpValueName
0x1800205c9  mov     [rsp+88h+samDesired], r9d; cbData
0x1800205ce  xor     r8d, r8d; Reserved
0x1800205d1  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1800205d6  call    cs:__imp_RegSetValueExW
0x1800205dc  mov     ebx, eax
0x1800205de  test    eax, eax
0x1800205e0  jz      short loc_18002065C
0x1800205e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205e9  lea     rax, WPP_GLOBAL_Control
0x1800205f0  cmp     rcx, rax
0x1800205f3  jz      short loc_18002065C
0x1800205f5  test    dword ptr [rcx+1Ch], 100h
0x1800205fc  jz      short loc_18002065C
0x1800205fe  cmp     byte ptr [rcx+19h], 1
0x180020602  jb      short loc_18002065C
0x180020604  mov     eax, dword ptr [rsp+88h+Data]
0x180020608  movzx   r9d, si
0x18002060c  mov     rcx, [rcx+10h]
0x180020610  mov     dword ptr [rsp+88h+lpSecurityAttributes], ebx
0x180020614  mov     [rsp+88h+samDesired], eax
0x180020618  mov     [rsp+88h+dwOptions], edi
0x18002061c  call    WPP_SF_HDDD
0x180020621  jmp     short loc_18002065C
0x180020623  mov     rcx, cs:WPP_GLOBAL_Control
0x18002062a  lea     rax, WPP_GLOBAL_Control
0x180020631  cmp     rcx, rax
0x180020634  jz      short loc_180020657
0x180020636  test    byte ptr [rcx+1Ch], 1
0x18002063a  jz      short loc_180020657
0x18002063c  cmp     byte ptr [rcx+19h], 1
0x180020640  jb      short loc_180020657
0x180020642  mov     rcx, [rcx+10h]
0x180020646  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x18002064d  mov     edx, 0Dh
0x180020652  call    WPP_SF_d
0x180020657  mov     ebx, 54Fh
0x18002065c  mov     rcx, [rsp+88h+hKey]; hKey
0x180020661  test    rcx, rcx
0x180020664  jz      short loc_18002066C
0x180020666  call    cs:__imp_RegCloseKey
0x18002066c  mov     eax, ebx
0x18002066e  mov     rcx, [rsp+88h+var_10]
0x180020673  xor     rcx, rsp; StackCookie
0x180020676  call    __security_check_cookie
0x18002067b  lea     r11, [rsp+88h+var_8]
0x180020683  mov     rbx, [r11+18h]
0x180020687  mov     rsi, [r11+20h]
0x18002068b  mov     rsp, r11
0x18002068e  pop     rdi
0x18002068f  retn
```
