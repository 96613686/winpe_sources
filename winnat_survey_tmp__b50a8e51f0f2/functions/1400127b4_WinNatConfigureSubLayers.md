# WinNatConfigureSubLayers

- ea: `0x1400127b4`
- end: `0x140012907`
- name: `WinNatConfigureSubLayers`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012100`
- `0x140012b9c`

## callees

- `0x14000caa0`
- `0x1400127b4`
- `0x14001ede0`
- `0x14001f440`

## import_xrefs

- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400128b1`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x1400128b1`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140012880`
- `fwpkclnt!FwpmSubLayerAdd0` at `0x140012880`
- `fwpkclnt!FwpmEngineClose0` at `0x1400128de`
- `fwpkclnt!FwpmEngineClose0` at `0x1400128de`
- `fwpkclnt!FwpmEngineOpen0` at `0x140012803`
- `fwpkclnt!FwpmEngineOpen0` at `0x140012803`

## pseudocode

```c
NTSTATUS __fastcall WinNatConfigureSubLayers(char a1)
{
  NTSTATUS result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  NTSTATUS v5; // edi
  __int64 i; // rsi
  GUID v7; // xmm0
  __int64 v8; // r14
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rcx
  HANDLE engineHandle; // [rsp+30h] [rbp-39h] BYREF
  FWPM_SUBLAYER0 subLayer; // [rsp+40h] [rbp-29h] BYREF

  engineHandle = 0;
  memset(&subLayer, 0, sizeof(subLayer));
  result = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v5 = result;
  if ( result >= 0 )
  {
    if ( a1 )
    {
      for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
      {
        if ( (WinNatCallouts[9 * i + 8] & 2) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3);
        memset(&subLayer, 0, sizeof(subLayer));
        v7 = *(GUID *)WinNatCallouts[9 * i + 2];
        subLayer.displayData = *(FWPM_DISPLAY_DATA0 *)&WinNatCallouts[9 * i + 4];
        subLayer.subLayerKey = v7;
        subLayer.flags = 0;
        v5 = FwpmSubLayerAdd0(engineHandle, &subLayer, 0);
        if ( v5 < 0 )
          break;
        LOBYTE(WinNatCallouts[9 * i + 8]) |= 2u;
      }
    }
    else
    {
      v8 = 0;
      v9 = 0;
      do
      {
        if ( (WinNatCallouts[v9 + 8] & 2) != 0 )
        {
          v5 = FwpmSubLayerDeleteByKey0(engineHandle, (const GUID *)WinNatCallouts[v9 + 2]);
          if ( v5 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10);
          LOBYTE(WinNatCallouts[v9 + 8]) &= ~2u;
        }
        ++v8;
        v9 += 9;
      }
      while ( v8 != 3 );
    }
    FwpmEngineClose0(engineHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1400127b4  push    rbp
0x1400127b6  push    rbx
0x1400127b7  push    rsi
0x1400127b8  push    rdi
0x1400127b9  push    r14
0x1400127bb  lea     rbp, [rsp-37h]
0x1400127c0  sub     rsp, 0A0h
0x1400127c7  mov     rax, cs:__security_cookie
0x1400127ce  xor     rax, rsp
0x1400127d1  mov     [rbp+57h+var_30], rax
0x1400127d5  xor     edx, edx; Val
0x1400127d7  mov     [rbp+57h+var_90], 0
0x1400127df  mov     bl, cl
0x1400127e1  lea     rcx, [rbp+57h+subLayer]; void *
0x1400127e5  lea     r8d, [rdx+48h]; Size
0x1400127e9  call    memset
0x1400127ee  xor     r9d, r9d; session
0x1400127f1  lea     rax, [rbp+57h+var_90]
0x1400127f5  xor     r8d, r8d; authIdentity
0x1400127f8  mov     [rsp+0C0h+engineHandle], rax; engineHandle
0x1400127fd  xor     ecx, ecx; serverName
0x1400127ff  lea     edx, [r9+0Ah]; authnService
0x140012803  call    cs:__imp_FwpmEngineOpen0
0x14001280a  nop     dword ptr [rax+rax+00h]
0x14001280f  mov     edi, eax
0x140012811  test    eax, eax
0x140012813  js      loc_1400128EC
0x140012819  test    bl, bl
0x14001281b  lea     rbx, WinNatCallouts
0x140012822  jz      short loc_14001289C
0x140012824  xor     esi, esi
0x140012826  cmp     esi, 3
0x140012829  jnb     loc_1400128DA
0x14001282f  lea     r14, [rsi+rsi*8]
0x140012833  test    byte ptr [rbx+r14*8+40h], 2
0x140012839  jz      short loc_140012840
0x14001283b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012840  xor     edx, edx; Val
0x140012842  lea     rcx, [rbp+57h+subLayer]; void *
0x140012846  lea     r8d, [rdx+48h]; Size
0x14001284a  call    memset
0x14001284f  mov     rax, [rbx+r14*8+10h]
0x140012854  lea     rdx, [rbp+57h+subLayer]; subLayer
0x140012858  mov     rcx, [rbp+57h+var_90]; engineHandle
0x14001285c  xor     r8d, r8d; sd
0x14001285f  movups  xmm0, xmmword ptr [rax]
0x140012862  mov     rax, [rbx+r14*8+20h]
0x140012867  mov     [rbp+57h+subLayer.displayData.name], rax
0x14001286b  mov     rax, [rbx+r14*8+28h]
0x140012870  mov     [rbp+57h+subLayer.displayData.description], rax
0x140012874  movdqu  xmmword ptr [rbp+57h+subLayer.subLayerKey.Data1], xmm0
0x140012879  mov     [rbp+57h+subLayer.flags], 0
0x140012880  call    cs:__imp_FwpmSubLayerAdd0
0x140012887  nop     dword ptr [rax+rax+00h]
0x14001288c  mov     edi, eax
0x14001288e  test    eax, eax
0x140012890  js      short loc_1400128DA
0x140012892  or      byte ptr [rbx+r14*8+40h], 2
0x140012898  inc     esi
0x14001289a  jmp     short loc_140012826
0x14001289c  xor     r14d, r14d
0x14001289f  xor     esi, esi
0x1400128a1  test    byte ptr [rsi+rbx+40h], 2
0x1400128a6  jz      short loc_1400128CD
0x1400128a8  mov     rdx, [rsi+rbx+10h]; key
0x1400128ad  mov     rcx, [rbp+57h+var_90]; engineHandle
0x1400128b1  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x1400128b8  nop     dword ptr [rax+rax+00h]
0x1400128bd  mov     edi, eax
0x1400128bf  test    eax, eax
0x1400128c1  jns     short loc_1400128C8
0x1400128c3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400128c8  and     byte ptr [rsi+rbx+40h], 0FDh
0x1400128cd  inc     r14
0x1400128d0  add     rsi, 48h ; 'H'
0x1400128d4  cmp     r14, 3
0x1400128d8  jnz     short loc_1400128A1
0x1400128da  mov     rcx, [rbp+57h+var_90]; engineHandle
0x1400128de  call    cs:__imp_FwpmEngineClose0
0x1400128e5  nop     dword ptr [rax+rax+00h]
0x1400128ea  mov     eax, edi
0x1400128ec  mov     rcx, [rbp+57h+var_30]
0x1400128f0  xor     rcx, rsp; StackCookie
0x1400128f3  call    __security_check_cookie
0x1400128f8  add     rsp, 0A0h
0x1400128ff  pop     r14
0x140012901  pop     rdi
0x140012902  pop     rsi
0x140012903  pop     rbx
0x140012904  pop     rbp
0x140012905  retn
```
