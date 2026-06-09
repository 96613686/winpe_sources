# SerializeToBuffer<_SPP_EXTERNAL_SNAPSHOT_PROP>(ulong *,uchar * *,void (*)(void *,_SPP_EXTERNAL_SNAPSHOT_PROP *),_GUID const *,_SPP_EXTERNAL_SNAPSHOT_PROP *)

- ea: `0x1800225a0`
- end: `0x180022796`
- name: `??$SerializeToBuffer@U_SPP_EXTERNAL_SNAPSHOT_PROP@@@@YAJPEAKPEAPEAEP6AXPEAXPEAU_SPP_EXTERNAL_SNAPSHOT_PROP@@@ZPEBU_GUID@@3@Z`
- size: `502`
- prototype: `__int64(_DWORD *, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006110`

## callees

- `0x180020710`
- `0x180022500`
- `0x1800225a0`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b82`
- `0x180035b9a`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180022722`
- `ntdll!RtlComputeCrc32` at `0x180022722`
- `RPCRT4!MesHandleFree` at `0x180022750`
- `RPCRT4!MesHandleFree` at `0x180022750`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180022692`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180022692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800226ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800226ce`

## pseudocode

```c
__int64 SerializeToBuffer<_SPP_EXTERNAL_SNAPSHOT_PROP>(_DWORD *a1, _QWORD *a2, ...)
{
  __int16 v4; // ax
  __int64 v5; // rsi
  int v6; // eax
  bool v7; // sf
  _DWORD *v8; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  handle_t pHandle; // [rsp+80h] [rbp+20h] BYREF
  char *pBuffer; // [rsp+90h] [rbp+30h] BYREF
  va_list pBuffera; // [rsp+90h] [rbp+30h]
  __int64 pEncodedSize; // [rsp+98h] [rbp+38h] BYREF
  va_list pEncodedSizea; // [rsp+98h] [rbp+38h]
  __int64 v20; // [rsp+A0h] [rbp+40h]
  va_list va2; // [rsp+A8h] [rbp+48h] BYREF

  va_start(va2, a2);
  va_start(pEncodedSizea, a2);
  va_start(pBuffera, a2);
  pBuffer = va_arg(pEncodedSizea, char *);
  va_copy(va2, pEncodedSizea);
  pEncodedSize = va_arg(va2, _QWORD);
  v20 = va_arg(va2, _QWORD);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SerializeToBuffer", 0xF6u, 1u);
  pBuffer = 0;
  LODWORD(pEncodedSize) = 0;
  pHandle = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  v4 = 258;
  if ( !a1 )
    goto LABEL_9;
  v13 = 258;
  if ( !a2 )
  {
    v4 = 259;
LABEL_9:
    v12 = -2147024809;
LABEL_10:
    v14 = v4;
    goto LABEL_20;
  }
  v5 = v20;
  v13 = 261;
  v4 = 262;
  if ( !v20 )
    goto LABEL_9;
  v12 = 0;
  v13 = 262;
  v6 = MesEncodeDynBufferHandleCreate((char **)pBuffera, (unsigned int *)pEncodedSizea, &pHandle);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  v12 = v6;
  v7 = v6 < 0;
  v4 = 264;
  if ( v7 )
    goto LABEL_10;
  v13 = 264;
  InvokeCoder<_SPP_METADATA_PROP>(pHandle, SPP_EXTERNAL_SNAPSHOT_PROP_Encode, v5);
  v8 = CoTaskMemAlloc((unsigned int)pEncodedSize + 24LL);
  v4 = 272;
  if ( !v8 )
  {
    v12 = -2147024882;
    goto LABEL_10;
  }
  v12 = 0;
  v13 = 272;
  memset_0(v8, 0, (unsigned int)pEncodedSize + 24LL);
  *(_OWORD *)v8 = xmmword_18003C2D0;
  v8[4] = RtlComputeCrc32(0x5EED5FA5u, (PUCHAR)pBuffer, pEncodedSize);
  memcpy_0(v8 + 6, pBuffer, (unsigned int)pEncodedSize);
  v9 = pEncodedSize + 24;
  *a2 = v8;
  *a1 = v9;
LABEL_20:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  CoTaskMemFree(pBuffer);
  pBuffer = 0;
  CoTaskMemFree(0);
  v10 = v12;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v10;
}

```

## disassembly

```asm
0x1800225a0  mov     [rsp-18h+arg_8], rbx
0x1800225a5  mov     [rsp-18h+pEncodedSize], r9
0x1800225aa  mov     [rsp-18h+pBuffer], r8
0x1800225af  push    rbp
0x1800225b0  push    rsi
0x1800225b1  push    rdi
0x1800225b2  mov     rbp, rsp
0x1800225b5  sub     rsp, 60h
0x1800225b9  mov     rbx, rdx
0x1800225bc  mov     rdi, rcx
0x1800225bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225c6  lea     rax, WPP_GLOBAL_Control
0x1800225cd  cmp     rcx, rax
0x1800225d0  jz      short loc_1800225F0
0x1800225d2  test    dword ptr [rcx+1Ch], 20000000h
0x1800225d9  jz      short loc_1800225F0
0x1800225db  mov     rcx, [rcx+10h]
0x1800225df  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x1800225e6  mov     edx, 12h
0x1800225eb  call    WPP_SF_
0x1800225f0  mov     r9d, 1; unsigned __int16
0x1800225f6  lea     rdx, aSerializetobuf; "SerializeToBuffer"
0x1800225fd  mov     r8d, 0F6h; unsigned __int16
0x180022603  lea     rcx, [rbp+var_40]; this
0x180022607  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002260c  mov     [rbp+pBuffer], 0
0x180022614  mov     dword ptr [rbp+pEncodedSize], 0
0x18002261b  mov     [rbp+pHandle], 0
0x180022623  test    rdi, rdi
0x180022626  jz      short loc_18002262E
0x180022628  mov     dword ptr [rdi], 0
0x18002262e  test    rbx, rbx
0x180022631  jz      short loc_18002263A
0x180022633  mov     qword ptr [rbx], 0
0x18002263a  mov     eax, 102h
0x18002263f  test    rdi, rdi
0x180022642  jnz     short loc_180022654
0x180022644  mov     [rbp+var_40], 80070057h
0x18002264b  mov     [rbp+var_3A], ax
0x18002264f  jmp     loc_180022747
0x180022654  mov     [rbp+var_3C], ax
0x180022658  test    rbx, rbx
0x18002265b  jnz     short loc_180022664
0x18002265d  mov     eax, 103h
0x180022662  jmp     short loc_180022644
0x180022664  mov     rsi, [rbp+arg_20]
0x180022668  mov     eax, 105h
0x18002266d  mov     [rbp+var_3C], ax
0x180022671  mov     eax, 106h
0x180022676  test    rsi, rsi
0x180022679  jz      short loc_180022644
0x18002267b  lea     r8, [rbp+pHandle]; pHandle
0x18002267f  mov     [rbp+var_40], 0
0x180022686  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x18002268a  mov     [rbp+var_3C], ax
0x18002268e  lea     rcx, [rbp+pBuffer]; pBuffer
0x180022692  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180022698  test    eax, eax
0x18002269a  jle     short loc_1800226A4
0x18002269c  movzx   eax, ax
0x18002269f  or      eax, 80070000h
0x1800226a4  mov     [rbp+var_40], eax
0x1800226a7  test    eax, eax
0x1800226a9  mov     eax, 108h
0x1800226ae  js      short loc_18002264B
0x1800226b0  mov     rcx, [rbp+pHandle]
0x1800226b4  lea     rdx, SPP_EXTERNAL_SNAPSHOT_PROP_Encode
0x1800226bb  mov     r8, rsi
0x1800226be  mov     [rbp+var_3C], ax
0x1800226c2  call    ??$InvokeCoder@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@Z1@Z; InvokeCoder<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_SPP_METADATA_PROP *)
0x1800226c7  mov     ecx, dword ptr [rbp+pEncodedSize]
0x1800226ca  add     rcx, 18h; cb
0x1800226ce  call    cs:__imp_CoTaskMemAlloc
0x1800226d4  mov     rsi, rax
0x1800226d7  test    rax, rax
0x1800226da  mov     eax, 110h
0x1800226df  jnz     short loc_1800226ED
0x1800226e1  mov     [rbp+var_40], 8007000Eh
0x1800226e8  jmp     loc_18002264B
0x1800226ed  mov     r8d, dword ptr [rbp+pEncodedSize]
0x1800226f1  xor     edx, edx; Val
0x1800226f3  add     r8, 18h; Size
0x1800226f7  mov     [rbp+var_40], 0
0x1800226fe  mov     rcx, rsi; void *
0x180022701  mov     [rbp+var_3C], ax
0x180022705  call    memset_0
0x18002270a  movups  xmm0, cs:xmmword_18003C2D0
0x180022711  mov     ecx, 5EED5FA5h; InitialCrc
0x180022716  movdqu  xmmword ptr [rsi], xmm0
0x18002271a  mov     r8d, dword ptr [rbp+pEncodedSize]; Length
0x18002271e  mov     rdx, [rbp+pBuffer]; Buffer
0x180022722  call    cs:__imp_RtlComputeCrc32
0x180022728  mov     [rsi+10h], eax
0x18002272b  lea     rcx, [rsi+18h]; void *
0x18002272f  mov     r8d, dword ptr [rbp+pEncodedSize]; Size
0x180022733  mov     rdx, [rbp+pBuffer]; Src
0x180022737  call    memcpy_0
0x18002273c  mov     eax, dword ptr [rbp+pEncodedSize]
0x18002273f  add     eax, 18h
0x180022742  mov     [rbx], rsi
0x180022745  mov     [rdi], eax
0x180022747  mov     rcx, [rbp+pHandle]; Handle
0x18002274b  test    rcx, rcx
0x18002274e  jz      short loc_18002275E
0x180022750  call    cs:__imp_MesHandleFree
0x180022756  mov     [rbp+pHandle], 0
0x18002275e  mov     rcx, [rbp+pBuffer]; pv
0x180022762  call    cs:__imp_CoTaskMemFree
0x180022768  xor     ecx, ecx; pv
0x18002276a  mov     [rbp+pBuffer], 0
0x180022772  call    cs:__imp_CoTaskMemFree
0x180022778  mov     ebx, [rbp+var_40]
0x18002277b  lea     rcx, [rbp+var_40]; this
0x18002277f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180022784  mov     eax, ebx
0x180022786  mov     rbx, [rsp+60h+arg_8]
0x18002278e  add     rsp, 60h
0x180022792  pop     rdi
0x180022793  pop     rsi
0x180022794  pop     rbp
0x180022795  retn
```
