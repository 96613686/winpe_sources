# SamILoadDownlevelDatabase

- ea: `0x180071870`
- end: `0x180071ae0`
- name: `SamILoadDownlevelDatabase`
- size: `624`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x1800372ac`
- `0x18006fdbc`
- `0x180071870`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1800719f5`
- `ntdll!RtlAdjustPrivilege` at `0x180071a46`
- `ntdll!RtlAdjustPrivilege` at `0x1800719f5`
- `ntdll!RtlAdjustPrivilege` at `0x180071a46`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180071a10`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180071a31`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180071a10`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180071a31`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180071911`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180071911`

## string_xrefs

- `0x18007195b`: `\system32\config\SAM.UPG`
- `0x1800719ab`: `\system32\config\SAM.SAV`
- `0x18007189d`: `\Registry\Machine\SAMUPGRADE`

## pseudocode

```c
__int64 __fastcall SamILoadDownlevelDatabase(unsigned int *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  WCHAR *v4; // rax
  __int64 v5; // rcx
  DWORD EnvironmentVariableW; // eax
  size_t v7; // rbx
  unsigned int KeyW; // ebx
  PUNICODE_STRING v9; // rcx
  unsigned __int8 OldValue[16]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR File[8]; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v14[32]; // [rsp+260h] [rbp+160h]
  WCHAR v15[8]; // [rsp+460h] [rbp+360h] BYREF
  _OWORD v16[32]; // [rsp+470h] [rbp+370h]

  OldValue[0] = 0;
  v2 = SampRegistryDelnode(L"\\Registry\\Machine\\SAMUPGRADE");
  if ( (int)(v2 + 0x80000000) >= 0
    && v2 != -1073741772
    && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 64, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v2);
  }
  v3 = 0;
  v4 = Buffer;
  v5 = 520;
  do
  {
    *(_BYTE *)v4 = 0;
    v4 = (WCHAR *)((char *)v4 + 1);
    --v5;
  }
  while ( v5 );
  EnvironmentVariableW = GetEnvironmentVariableW(L"systemroot", Buffer, 0x104u);
  if ( EnvironmentVariableW - 1 > 0x81 )
  {
    EnvironmentVariableW = 10;
    wcscpy(Buffer, L"c:\\winows");
  }
  v7 = 2LL * EnvironmentVariableW;
  memcpy_0(File, Buffer, v7);
  *(_OWORD *)&File[v7 / 2] = *(_OWORD *)L"\\system32\\config\\SAM.UPG";
  *(_OWORD *)((char *)v14 + v7) = *(_OWORD *)L"2\\config\\SAM.UPG";
  *(_OWORD *)((char *)&v14[1] + v7) = *(_OWORD *)L"\\SAM.UPG";
  *(_WORD *)((char *)&v14[2] + v7) = aSystem32Config[24];
  memcpy_0(v15, Buffer, v7);
  *(_OWORD *)&v15[v7 / 2] = *(_OWORD *)L"\\system32\\config\\SAM.SAV";
  *(_OWORD *)((char *)v16 + v7) = *(_OWORD *)L"2\\config\\SAM.SAV";
  *(_OWORD *)((char *)&v16[1] + v7) = *(_OWORD *)L"\\SAM.SAV";
  *(_WORD *)((char *)&v16[2] + v7) = aSystem32Config_1[24];
  RtlAdjustPrivilege(0x12u, 1u, 0, OldValue);
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"SAMUPGRADE", File);
  if ( KeyW )
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"SAMUPGRADE", v15);
  RtlAdjustPrivilege(0x12u, 0, 0, OldValue);
  if ( KeyW )
  {
    v9 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 65, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, KeyW);
      v9 = WPP_GLOBAL_Control;
    }
    v3 = -1073741823;
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    *a1 = KeyW;
    v9 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v9[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v9[3].Buffer, 66, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v3, v3);
  return v3;
}

```

## disassembly

```asm
0x180071870  push    rbp
0x180071872  push    rbx
0x180071873  push    rsi
0x180071874  push    rdi
0x180071875  lea     rbp, [rsp-588h]
0x18007187d  sub     rsp, 688h
0x180071884  mov     rax, cs:__security_cookie
0x18007188b  xor     rax, rsp
0x18007188e  mov     [rbp+5A0h+var_30], rax
0x180071895  mov     rsi, rcx
0x180071898  mov     [rsp+6A0h+OldValue], 0
0x18007189d  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SAMUPGRADE"
0x1800718a4  call    ?SampRegistryDelnode@@YAJPEBG@Z; SampRegistryDelnode(ushort const *)
0x1800718a9  mov     edx, 80000000h
0x1800718ae  lea     ecx, [rax+rdx]
0x1800718b1  test    edx, ecx
0x1800718b3  jnz     short loc_1800718E7
0x1800718b5  cmp     eax, 0C0000034h
0x1800718ba  jz      short loc_1800718E7
0x1800718bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800718c3  test    byte ptr [rcx+44h], 80h
0x1800718c7  jz      short loc_1800718E7
0x1800718c9  cmp     byte ptr [rcx+41h], 2
0x1800718cd  jb      short loc_1800718E7
0x1800718cf  mov     rcx, [rcx+38h]
0x1800718d3  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x1800718da  mov     edx, 40h ; '@'
0x1800718df  mov     r9d, eax
0x1800718e2  call    WPP_SF_d
0x1800718e7  xor     edi, edi
0x1800718e9  lea     rax, [rsp+6A0h+Buffer]
0x1800718ee  mov     ecx, 208h
0x1800718f3  mov     [rax], dil
0x1800718f6  inc     rax
0x1800718f9  sub     rcx, 1
0x1800718fd  jnz     short loc_1800718F3
0x1800718ff  mov     r8d, 104h; nSize
0x180071905  lea     rdx, [rsp+6A0h+Buffer]; lpBuffer
0x18007190a  lea     rcx, Name; "systemroot"
0x180071911  call    cs:__imp_GetEnvironmentVariableW
0x180071917  lea     ecx, [rax-1]
0x18007191a  cmp     ecx, 81h
0x180071920  jbe     short loc_180071941
0x180071922  movups  xmm0, xmmword ptr cs:aCWindows; "c:\\windows"
0x180071929  mov     eax, 0Ah
0x18007192e  movsd   xmm1, qword ptr cs:aCWindows+0Eh; "ows"
0x180071936  movaps  xmmword ptr [rsp+6A0h+Buffer], xmm0
0x18007193b  movsd   qword ptr [rsp+6A0h+Buffer+0Eh], xmm1
0x180071941  mov     eax, eax
0x180071943  lea     rdx, [rsp+6A0h+Buffer]; Src
0x180071948  lea     rcx, [rbp+5A0h+File]; void *
0x18007194f  lea     rbx, [rax+rax]
0x180071953  mov     r8, rbx; Size
0x180071956  call    memcpy_0
0x18007195b  movups  xmm0, xmmword ptr cs:aSystem32Config; "\\system32\\config\\SAM.UPG"
0x180071962  movzx   eax, word ptr cs:aSystem32Config+30h; ""
0x180071969  mov     r8, rbx; Size
0x18007196c  movups  xmm1, xmmword ptr cs:aSystem32Config+10h; "2\\config\\SAM.UPG"
0x180071973  lea     rdx, [rsp+6A0h+Buffer]; Src
0x180071978  movups  xmmword ptr [rbp+rbx+5A0h+File], xmm0
0x180071980  lea     rcx, [rbp+5A0h+var_240]; void *
0x180071987  movups  xmm0, xmmword ptr cs:aSystem32Config+20h; "\\SAM.UPG"
0x18007198e  movups  [rbp+rbx+5A0h+var_440], xmm1
0x180071996  movups  [rbp+rbx+5A0h+var_430], xmm0
0x18007199e  mov     [rbp+rbx+5A0h+var_420], ax
0x1800719a6  call    memcpy_0
0x1800719ab  movups  xmm0, xmmword ptr cs:aSystem32Config_1; "\\system32\\config\\SAM.SAV"
0x1800719b2  movzx   eax, word ptr cs:aSystem32Config_1+30h; ""
0x1800719b9  xor     r8d, r8d; ForThread
0x1800719bc  movups  xmm1, xmmword ptr cs:aSystem32Config_1+10h; "2\\config\\SAM.SAV"
0x1800719c3  lea     r9, [rsp+6A0h+OldValue]; OldValue
0x1800719c8  mov     dl, 1; NewValue
0x1800719ca  movups  xmmword ptr [rbp+rbx+5A0h+var_240], xmm0
0x1800719d2  lea     ecx, [r8+12h]; Privilege
0x1800719d6  movups  xmm0, xmmword ptr cs:aSystem32Config_1+20h; "\\SAM.SAV"
0x1800719dd  movups  [rbp+rbx+5A0h+var_230], xmm1
0x1800719e5  movups  [rbp+rbx+5A0h+var_220], xmm0
0x1800719ed  mov     [rbp+rbx+5A0h+var_210], ax
0x1800719f5  call    cs:__imp_RtlAdjustPrivilege
0x1800719fb  lea     r8, [rbp+5A0h+File]; lpFile
0x180071a02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071a09  lea     rdx, aSamupgrade; "SAMUPGRADE"
0x180071a10  call    cs:__imp_RegLoadKeyW
0x180071a16  mov     ebx, eax
0x180071a18  test    eax, eax
0x180071a1a  jz      short loc_180071A39
0x180071a1c  lea     r8, [rbp+5A0h+var_240]; lpFile
0x180071a23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071a2a  lea     rdx, aSamupgrade; "SAMUPGRADE"
0x180071a31  call    cs:__imp_RegLoadKeyW
0x180071a37  mov     ebx, eax
0x180071a39  xor     edx, edx; NewValue
0x180071a3b  lea     r9, [rsp+6A0h+OldValue]; OldValue
0x180071a40  xor     r8d, r8d; ForThread
0x180071a43  lea     ecx, [rdx+12h]; Privilege
0x180071a46  call    cs:__imp_RtlAdjustPrivilege
0x180071a4c  test    ebx, ebx
0x180071a4e  jz      short loc_180071A89
0x180071a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180071a57  test    byte ptr [rcx+44h], 80h
0x180071a5b  jz      short loc_180071A82
0x180071a5d  cmp     byte ptr [rcx+41h], 2
0x180071a61  jb      short loc_180071A82
0x180071a63  mov     rcx, [rcx+38h]
0x180071a67  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071a6e  mov     edx, 41h ; 'A'
0x180071a73  mov     r9d, ebx
0x180071a76  call    WPP_SF_d
0x180071a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180071a82  mov     edi, 0C0000001h
0x180071a87  jmp     short loc_180071A90
0x180071a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180071a90  test    rsi, rsi
0x180071a93  jz      short loc_180071A9E
0x180071a95  mov     [rsi], ebx
0x180071a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180071a9e  test    dword ptr [rcx+44h], 20000h
0x180071aa5  jz      short loc_180071AC3
0x180071aa7  mov     rcx, [rcx+38h]
0x180071aab  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071ab2  mov     edx, 42h ; 'B'
0x180071ab7  mov     [rsp+6A0h+var_680], edi
0x180071abb  mov     r9d, edi
0x180071abe  call    WPP_SF_Dd
0x180071ac3  mov     eax, edi
0x180071ac5  mov     rcx, [rbp+5A0h+var_30]
0x180071acc  xor     rcx, rsp; StackCookie
0x180071acf  call    __security_check_cookie
0x180071ad4  add     rsp, 688h
0x180071adb  pop     rdi
0x180071adc  pop     rsi
0x180071add  pop     rbx
0x180071ade  pop     rbp
0x180071adf  retn
```
