# CVssFunctionTracer::~CVssFunctionTracer(void)

- ea: `0x1400137c0`
- end: `0x1400138d0`
- name: `??1CVssFunctionTracer@@QEAA@XZ`
- size: `272`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `637`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001d90`
- `0x140002270`
- `0x140003014`
- `0x140003320`
- `0x1400037bc`
- `0x140003b70`
- `0x14000400c`
- `0x1400041bc`
- `0x140004690`
- `0x140005050`
- `0x140005c38`
- `0x140006078`
- `0x140006270`
- `0x140007060`
- `0x140007250`
- `0x140008a3c`
- `0x140008cd0`
- `0x140008f7c`
- `0x1400090d0`
- `0x140009b50`
- `0x140009ea0`
- `0x14000a988`
- `0x14000ac50`
- `0x14000b140`
- `0x14000bc1c`
- `0x14000c0a0`
- `0x14000c84c`
- `0x14000dcd0`
- `0x14000e670`
- `0x14000f1d0`
- `0x14000fba0`
- `0x140010200`
- `0x140010d70`
- `0x140011ae0`
- `0x140014650`
- `0x140014ff0`
- `0x140015fb0`
- `0x140016db0`
- `0x14001818c`
- `0x14001940c`
- `0x140019eb0`
- `0x14001b9f0`
- `0x14001c878`
- `0x14001cafc`
- `0x14001d41c`
- `0x14001d750`
- `0x14001d810`
- `0x14001e91c`
- `0x140024500`
- `0x1400272d8`

## callees

- `0x1400138e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013806`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013806`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400138c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400137fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall CVssFunctionTracer::~CVssFunctionTracer(LPVOID *this)
{
  DWORD TickCount; // eax
  unsigned int v3; // r8d
  DWORD v4; // esi
  unsigned int v5; // edi
  unsigned int v6; // [rsp+20h] [rbp-58h]
  unsigned int v7; // [rsp+28h] [rbp-50h]
  unsigned int v8; // [rsp+30h] [rbp-48h]
  int v9; // [rsp+38h] [rbp-40h]
  DWORD v10; // [rsp+40h] [rbp-38h]
  int v11; // [rsp+48h] [rbp-30h]

  CoTaskMemFree(this[8]);
  this[8] = 0;
  CoTaskMemFree(this[9]);
  this[9] = 0;
  CoTaskMemFree(this[10]);
  this[10] = 0;
  CoTaskMemFree(this[11]);
  this[11] = 0;
  TickCount = GetTickCount();
  v3 = 160;
  v4 = TickCount - *((_DWORD *)this + 13);
  v10 = v4;
  v5 = v4 / 0x3E8;
  if ( *((_DWORD *)this + 14) != 255 )
    v3 = *((_DWORD *)this + 14);
  v9 = TickCount - *((_DWORD *)this + 13) - 1000 * v5;
  v8 = v5 % 0x3C;
  v7 = v4 / 0xEA60 % 0x3C;
  v6 = v4 / 0x36EE80 % 0x3C;
  v11 = *((_DWORD *)this + 2);
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)this,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v6,
    v7,
    v8,
    v9,
    v10,
    v11);
  VssSetTracingContextPerThread(this[12]);
}

```

## disassembly

```asm
0x1400137c0  push    rbx
0x1400137c2  push    rbp
0x1400137c3  push    rsi
0x1400137c4  push    rdi
0x1400137c5  sub     rsp, 58h
0x1400137c9  mov     rbp, rcx
0x1400137cc  mov     rcx, [rcx+40h]; pv
0x1400137d0  call    cs:__imp_CoTaskMemFree
0x1400137d6  xor     ebx, ebx
0x1400137d8  mov     [rbp+40h], rbx
0x1400137dc  mov     rcx, [rbp+48h]; pv
0x1400137e0  call    cs:__imp_CoTaskMemFree
0x1400137e6  mov     [rbp+48h], rbx
0x1400137ea  mov     rcx, [rbp+50h]; pv
0x1400137ee  call    cs:__imp_CoTaskMemFree
0x1400137f4  mov     [rbp+50h], rbx
0x1400137f8  mov     rcx, [rbp+58h]; pv
0x1400137fc  call    cs:__imp_CoTaskMemFree
0x140013802  mov     [rbp+58h], rbx
0x140013806  call    cs:__imp_GetTickCount
0x14001380c  mov     r9d, [rbp+8]
0x140013810  mov     r8d, 0A0h
0x140013816  mov     esi, eax
0x140013818  mov     [rsp+78h+var_30], r9d
0x14001381d  sub     esi, [rbp+34h]
0x140013820  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140013827  mov     eax, 10624DD3h
0x14001382c  mov     [rsp+78h+var_38], esi
0x140013830  mul     esi
0x140013832  mov     eax, 88888889h
0x140013837  mov     edi, edx
0x140013839  shr     edi, 6
0x14001383c  mul     edi
0x14001383e  mov     eax, 45E7B273h
0x140013843  mov     ebx, edi
0x140013845  shr     edx, 5
0x140013848  imul    ecx, edx, 3Ch ; '<'
0x14001384b  mul     esi
0x14001384d  sub     ebx, ecx
0x14001384f  mov     eax, 88888889h
0x140013854  mov     r11d, edx
0x140013857  shr     r11d, 0Eh
0x14001385b  mul     r11d
0x14001385e  mov     eax, 95217CB1h
0x140013863  shr     edx, 5
0x140013866  imul    ecx, edx, 3Ch ; '<'
0x140013869  mul     esi
0x14001386b  sub     r11d, ecx
0x14001386e  mov     eax, 88888889h
0x140013873  mov     r10d, edx
0x140013876  mov     ecx, esi
0x140013878  shr     r10d, 15h
0x14001387c  mul     r10d
0x14001387f  shr     edx, 5
0x140013882  imul    eax, edx, 3Ch ; '<'
0x140013885  lea     rdx, aExit; "EXIT"
0x14001388c  sub     r10d, eax
0x14001388f  cmp     dword ptr [rbp+38h], 0FFh
0x140013896  cmovnz  r8d, [rbp+38h]; unsigned int
0x14001389b  imul    eax, edi, 3E8h
0x1400138a1  sub     ecx, eax
0x1400138a3  mov     [rsp+78h+var_40], ecx
0x1400138a7  mov     rcx, rbp; this
0x1400138aa  mov     [rsp+78h+var_48], ebx
0x1400138ae  mov     [rsp+78h+var_50], r11d
0x1400138b3  mov     [rsp+78h+var_58], r10d
0x1400138b8  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400138bd  mov     rcx, [rbp+60h]
0x1400138c1  add     rsp, 58h
0x1400138c5  pop     rdi
0x1400138c6  pop     rsi
0x1400138c7  pop     rbp
0x1400138c8  pop     rbx
0x1400138c9  jmp     cs:__imp_VssSetTracingContextPerThread
```
