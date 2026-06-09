# WinNatConfigureSubLayers

- ea: `0x1400130f4`
- end: `0x140013247`
- name: `WinNatConfigureSubLayers`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012a40`
- `0x1400134dc`

## callees

- `0x14000caa0`
- `0x1400130f4`
- `0x14001f320`
- `0x14001f980`

## import_xrefs

- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400131f1`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400131f1`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x1400131c0`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x1400131c0`
- `fwpkclnt!FwpmEngineClose0` at `0x14001321e`
- `fwpkclnt!FwpmEngineClose0` at `0x14001321e`
- `fwpkclnt!FwpmEngineOpen0` at `0x140013143`
- `fwpkclnt!FwpmEngineOpen0` at `0x140013143`

## pseudocode

```c
NTSTATUS __fastcall WinNatConfigureSubLayers(char a1)
{
  NTSTATUS result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  NTSTATUS v6; // edi
  __int64 i; // rsi
  GUID v8; // xmm0
  __int64 v9; // r14
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  HANDLE engineHandle; // [rsp+30h] [rbp-39h] BYREF
  FWPM_SUBLAYER0 subLayer; // [rsp+40h] [rbp-29h] BYREF

  engineHandle = 0;
  memset(&subLayer, 0, sizeof(subLayer));
  result = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v6 = result;
  if ( result >= 0 )
  {
    if ( a1 )
    {
      for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
      {
        if ( (WinNatCallouts[9 * i + 8] & 2) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
        memset(&subLayer, 0, sizeof(subLayer));
        v8 = *(GUID *)WinNatCallouts[9 * i + 2];
        subLayer.displayData = *(FWPM_DISPLAY_DATA0 *)&WinNatCallouts[9 * i + 4];
        subLayer.subLayerKey = v8;
        subLayer.flags = 0;
        v6 = FwpmSubLayerAdd0(engineHandle, &subLayer, 0);
        if ( v6 < 0 )
          break;
        LOBYTE(WinNatCallouts[9 * i + 8]) |= 2u;
      }
    }
    else
    {
      v9 = 0;
      v10 = 0;
      do
      {
        if ( (WinNatCallouts[v10 + 8] & 2) != 0 )
        {
          v6 = FwpmSubLayerDeleteByKey0(engineHandle, (const GUID *)WinNatCallouts[v10 + 2]);
          if ( v6 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11, v13);
          LOBYTE(WinNatCallouts[v10 + 8]) &= ~2u;
        }
        ++v9;
        v10 += 9;
      }
      while ( v9 != 3 );
    }
    FwpmEngineClose0(engineHandle);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1400130f4  push    rbp
0x1400130f6  push    rbx
0x1400130f7  push    rsi
0x1400130f8  push    rdi
0x1400130f9  push    r14
0x1400130fb  lea     rbp, [rsp-37h]
0x140013100  sub     rsp, 0A0h
0x140013107  mov     rax, cs:__security_cookie
0x14001310e  xor     rax, rsp
0x140013111  mov     [rbp+57h+var_30], rax
0x140013115  xor     edx, edx; Val
0x140013117  mov     [rbp+57h+var_90], 0
0x14001311f  mov     bl, cl
0x140013121  lea     rcx, [rbp+57h+subLayer]; void *
0x140013125  lea     r8d, [rdx+48h]; Size
0x140013129  call    memset
0x14001312e  xor     r9d, r9d; session
0x140013131  lea     rax, [rbp+57h+var_90]
0x140013135  xor     r8d, r8d; authIdentity
0x140013138  mov     [rsp+0C0h+engineHandle], rax; engineHandle
0x14001313d  xor     ecx, ecx; serverName
0x14001313f  lea     edx, [r9+0Ah]; authnService
0x140013143  call    cs:__imp_FwpmEngineOpen0
0x14001314a  nop     dword ptr [rax+rax+00h]
0x14001314f  mov     edi, eax
0x140013151  test    eax, eax
0x140013153  js      loc_14001322C
0x140013159  test    bl, bl
0x14001315b  lea     rbx, WinNatCallouts
0x140013162  jz      short loc_1400131DC
0x140013164  xor     esi, esi
0x140013166  cmp     esi, 3
0x140013169  jnb     loc_14001321A
0x14001316f  lea     r14, [rsi+rsi*8]
0x140013173  test    byte ptr [rbx+r14*8+40h], 2
0x140013179  jz      short loc_140013180
0x14001317b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140013180  xor     edx, edx; Val
0x140013182  lea     rcx, [rbp+57h+subLayer]; void *
0x140013186  lea     r8d, [rdx+48h]; Size
0x14001318a  call    memset
0x14001318f  mov     rax, [rbx+r14*8+10h]
0x140013194  lea     rdx, [rbp+57h+subLayer]; subLayer
0x140013198  mov     rcx, [rbp+57h+var_90]; engineHandle
0x14001319c  xor     r8d, r8d; sd
0x14001319f  movups  xmm0, xmmword ptr [rax]
0x1400131a2  mov     rax, [rbx+r14*8+20h]
0x1400131a7  mov     [rbp+57h+subLayer.displayData.name], rax
0x1400131ab  mov     rax, [rbx+r14*8+28h]
0x1400131b0  mov     [rbp+57h+subLayer.displayData.description], rax
0x1400131b4  movdqu  xmmword ptr [rbp+57h+subLayer.subLayerKey.Data1], xmm0
0x1400131b9  mov     [rbp+57h+subLayer.flags], 0
0x1400131c0  call    cs:__imp_FwpmSubLayerAdd0
0x1400131c7  nop     dword ptr [rax+rax+00h]
0x1400131cc  mov     edi, eax
0x1400131ce  test    eax, eax
0x1400131d0  js      short loc_14001321A
0x1400131d2  or      byte ptr [rbx+r14*8+40h], 2
0x1400131d8  inc     esi
0x1400131da  jmp     short loc_140013166
0x1400131dc  xor     r14d, r14d
0x1400131df  xor     esi, esi
0x1400131e1  test    byte ptr [rsi+rbx+40h], 2
0x1400131e6  jz      short loc_14001320D
0x1400131e8  mov     rdx, [rsi+rbx+10h]; key
0x1400131ed  mov     rcx, [rbp+57h+var_90]; engineHandle
0x1400131f1  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x1400131f8  nop     dword ptr [rax+rax+00h]
0x1400131fd  mov     edi, eax
0x1400131ff  test    eax, eax
0x140013201  jns     short loc_140013208
0x140013203  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140013208  and     byte ptr [rsi+rbx+40h], 0FDh
0x14001320d  inc     r14
0x140013210  add     rsi, 48h ; 'H'
0x140013214  cmp     r14, 3
0x140013218  jnz     short loc_1400131E1
0x14001321a  mov     rcx, [rbp+57h+var_90]; engineHandle
0x14001321e  call    cs:__imp_FwpmEngineClose0
0x140013225  nop     dword ptr [rax+rax+00h]
0x14001322a  mov     eax, edi
0x14001322c  mov     rcx, [rbp+57h+var_30]
0x140013230  xor     rcx, rsp; StackCookie
0x140013233  call    __security_check_cookie
0x140013238  add     rsp, 0A0h
0x14001323f  pop     r14
0x140013241  pop     rdi
0x140013242  pop     rsi
0x140013243  pop     rbx
0x140013244  pop     rbp
0x140013245  retn
```
