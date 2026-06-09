# SafeStrClone(ushort const *)

- ea: `0x1400227a0`
- end: `0x1400228b4`
- name: `?SafeStrClone@@YAPEAGPEBG@Z`
- size: `276`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001f5fc`
- `0x140021cd8`
- `0x140022628`
- `0x1400235e0`
- `0x140058f70`
- `0x140059484`
- `0x140059980`
- `0x14005a294`
- `0x1400768c4`
- `0x1400d299c`
- `0x1400d616c`

## callees

- `0x1400227a0`
- `0x14005b208`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002286e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002287d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400228a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002286e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002287d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400228a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400227e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400227e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400228ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400228ac`

## pseudocode

```c
unsigned __int16 *__fastcall SafeStrClone(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rbx
  __int64 v2; // rax
  unsigned int v4; // edi
  unsigned int v5; // esi
  _WORD *v6; // rax
  _WORD *v7; // r14
  __int64 v8; // r8
  __int64 v9; // rdx
  _WORD *v10; // rcx
  _WORD *v11; // rax
  unsigned int v12; // eax
  DWORD v14; // eax

  v1 = a1;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v2 = -1;
  while ( a1[++v2] != 0 )
    ;
  v4 = v2 + 1;
  v5 = 2 * (v2 + 1);
  v6 = CoTaskMemAlloc(v5);
  v7 = v6;
  if ( !v6 )
  {
    SetLastError(0xEu);
    return 0;
  }
  memset_0(v6, 0, v5);
  v8 = v4;
  v9 = 2147483646;
  if ( v4 - 1 > 0x7FFFFFFE )
  {
    v12 = -2147024809;
    if ( v4 )
      *v7 = 0;
    goto LABEL_20;
  }
  v10 = v7;
  do
  {
    if ( !v9 )
      break;
    if ( !*v1 )
      break;
    *v10++ = *v1++;
    --v9;
    --v8;
  }
  while ( v8 );
  v11 = v10 - 1;
  if ( v8 )
    v11 = v10;
  *v11 = 0;
  v12 = -2147024774;
  if ( !v8 )
  {
LABEL_20:
    v14 = WIN32_FROM_HRESULT(v12);
    SetLastError(v14);
    CoTaskMemFree(v7);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1400227a0  push    rbx
0x1400227a2  sub     rsp, 20h
0x1400227a6  mov     rbx, rcx
0x1400227a9  test    rcx, rcx
0x1400227ac  jz      loc_140022878
0x1400227b2  mov     [rsp+28h+arg_0], rsi
0x1400227b7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400227be  mov     [rsp+28h+arg_8], rdi
0x1400227c3  mov     [rsp+28h+arg_10], r14
0x1400227c8  nop     dword ptr [rax+rax+00000000h]
0x1400227d0  cmp     word ptr [rcx+rax*2+2], 0
0x1400227d6  lea     rax, [rax+1]
0x1400227da  jnz     short loc_1400227D0
0x1400227dc  lea     edi, [rax+1]
0x1400227df  lea     eax, [rdi+rdi]
0x1400227e2  mov     ecx, eax; cb
0x1400227e4  mov     esi, eax
0x1400227e6  call    cs:__imp_CoTaskMemAlloc
0x1400227ec  mov     r14, rax
0x1400227ef  test    rax, rax
0x1400227f2  jz      short loc_140022869
0x1400227f4  mov     r8d, esi; Size
0x1400227f7  xor     edx, edx; Val
0x1400227f9  mov     rcx, rax; void *
0x1400227fc  call    memset_0
0x140022801  lea     ecx, [rdi-1]
0x140022804  mov     r8d, edi
0x140022807  mov     edx, 7FFFFFFEh
0x14002280c  cmp     ecx, edx
0x14002280e  ja      short loc_14002288B
0x140022810  mov     rcx, r14
0x140022813  test    rdx, rdx
0x140022816  jz      short loc_140022834
0x140022818  movzx   eax, word ptr [rbx]
0x14002281b  test    ax, ax
0x14002281e  jz      short loc_140022834
0x140022820  mov     [rcx], ax
0x140022823  add     rbx, 2
0x140022827  add     rcx, 2
0x14002282b  dec     rdx
0x14002282e  sub     r8, 1
0x140022832  jnz     short loc_140022813
0x140022834  test    r8, r8
0x140022837  lea     rax, [rcx-2]
0x14002283b  cmovnz  rax, rcx
0x14002283f  xor     ecx, ecx
0x140022841  test    r8, r8
0x140022844  mov     [rax], cx
0x140022847  mov     eax, 8007007Ah
0x14002284c  cmovnz  eax, ecx
0x14002284f  jz      short loc_14002289A
0x140022851  mov     rax, r14
0x140022854  mov     rdi, [rsp+28h+arg_8]
0x140022859  mov     rsi, [rsp+28h+arg_0]
0x14002285e  mov     r14, [rsp+28h+arg_10]
0x140022863  add     rsp, 20h
0x140022867  pop     rbx
0x140022868  retn
0x140022869  mov     ecx, 0Eh; dwErrCode
0x14002286e  call    cs:__imp_SetLastError
0x140022874  xor     eax, eax
0x140022876  jmp     short loc_140022854
0x140022878  mov     ecx, 57h ; 'W'; dwErrCode
0x14002287d  call    cs:__imp_SetLastError
0x140022883  xor     eax, eax
0x140022885  add     rsp, 20h
0x140022889  pop     rbx
0x14002288a  retn
0x14002288b  mov     eax, 80070057h
0x140022890  test    edi, edi
0x140022892  jz      short loc_14002289A
0x140022894  xor     ecx, ecx
0x140022896  mov     [r14], cx
0x14002289a  mov     ecx, eax
0x14002289c  call    WIN32_FROM_HRESULT
0x1400228a1  mov     ecx, eax; dwErrCode
0x1400228a3  call    cs:__imp_SetLastError
0x1400228a9  mov     rcx, r14; pv
0x1400228ac  call    cs:__imp_CoTaskMemFree
0x1400228b2  jmp     short loc_140022874
```
