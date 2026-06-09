# CAutoplayHandler::_Cleanup(void)

- ea: `0x18016ecf4`
- end: `0x18016ee12`
- name: `?_Cleanup@CAutoplayHandler@@AEAAXXZ`
- size: `286`
- prototype: `void __fastcall(CAutoplayHandler *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1803ad5cc`
- `0x1803af490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016eda1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016edaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016edbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016edce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ede2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ed93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016eda1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016edaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016edbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016edce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016ede2`

## pseudocode

```c
void __fastcall CAutoplayHandler::_Cleanup(LPVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  CoTaskMemFree(this[2]);
  v2 = this[3];
  this[2] = 0;
  CoTaskMemFree(v2);
  v3 = this[4];
  this[3] = 0;
  CoTaskMemFree(v3);
  v4 = this[5];
  this[4] = 0;
  CoTaskMemFree(v4);
  v5 = this[6];
  this[5] = 0;
  CoTaskMemFree(v5);
  v6 = this[7];
  this[6] = 0;
  CoTaskMemFree(v6);
  v7 = this[8];
  this[7] = 0;
  CoTaskMemFree(v7);
  v8 = this[9];
  this[8] = 0;
  CoTaskMemFree(v8);
  v9 = this[10];
  this[9] = 0;
  CoTaskMemFree(v9);
  v10 = this[11];
  this[10] = 0;
  CoTaskMemFree(v10);
  v11 = this[12];
  this[11] = 0;
  CoTaskMemFree(v11);
  v12 = this[13];
  this[12] = 0;
  CoTaskMemFree(v12);
  v13 = this[14];
  this[13] = 0;
  CoTaskMemFree(v13);
  v14 = this[15];
  this[14] = 0;
  CoTaskMemFree(v14);
  v15 = this[16];
  this[15] = 0;
  CoTaskMemFree(v15);
  v16 = this[17];
  this[16] = 0;
  CoTaskMemFree(v16);
  this[17] = 0;
  *((GUID *)this + 9) = GUID_NULL;
  this[20] = 0;
}

```

## disassembly

```asm
0x18016ecf4  mov     [rsp+arg_0], rbx
0x18016ecf9  push    rdi
0x18016ecfa  sub     rsp, 20h
0x18016ecfe  mov     rbx, rcx
0x18016ed01  mov     rcx, [rcx+10h]; pv
0x18016ed05  call    cs:__imp_CoTaskMemFree
0x18016ed0b  mov     rcx, [rbx+18h]; pv
0x18016ed0f  xor     edi, edi
0x18016ed11  mov     [rbx+10h], rdi
0x18016ed15  call    cs:__imp_CoTaskMemFree
0x18016ed1b  mov     rcx, [rbx+20h]; pv
0x18016ed1f  mov     [rbx+18h], rdi
0x18016ed23  call    cs:__imp_CoTaskMemFree
0x18016ed29  mov     rcx, [rbx+28h]; pv
0x18016ed2d  mov     [rbx+20h], rdi
0x18016ed31  call    cs:__imp_CoTaskMemFree
0x18016ed37  mov     rcx, [rbx+30h]; pv
0x18016ed3b  mov     [rbx+28h], rdi
0x18016ed3f  call    cs:__imp_CoTaskMemFree
0x18016ed45  mov     rcx, [rbx+38h]; pv
0x18016ed49  mov     [rbx+30h], rdi
0x18016ed4d  call    cs:__imp_CoTaskMemFree
0x18016ed53  mov     rcx, [rbx+40h]; pv
0x18016ed57  mov     [rbx+38h], rdi
0x18016ed5b  call    cs:__imp_CoTaskMemFree
0x18016ed61  mov     rcx, [rbx+48h]; pv
0x18016ed65  mov     [rbx+40h], rdi
0x18016ed69  call    cs:__imp_CoTaskMemFree
0x18016ed6f  mov     rcx, [rbx+50h]; pv
0x18016ed73  mov     [rbx+48h], rdi
0x18016ed77  call    cs:__imp_CoTaskMemFree
0x18016ed7d  mov     rcx, [rbx+58h]; pv
0x18016ed81  mov     [rbx+50h], rdi
0x18016ed85  call    cs:__imp_CoTaskMemFree
0x18016ed8b  mov     rcx, [rbx+60h]; pv
0x18016ed8f  mov     [rbx+58h], rdi
0x18016ed93  call    cs:__imp_CoTaskMemFree
0x18016ed99  mov     rcx, [rbx+68h]; pv
0x18016ed9d  mov     [rbx+60h], rdi
0x18016eda1  call    cs:__imp_CoTaskMemFree
0x18016eda7  mov     rcx, [rbx+70h]; pv
0x18016edab  mov     [rbx+68h], rdi
0x18016edaf  call    cs:__imp_CoTaskMemFree
0x18016edb5  mov     rcx, [rbx+78h]; pv
0x18016edb9  mov     [rbx+70h], rdi
0x18016edbd  call    cs:__imp_CoTaskMemFree
0x18016edc3  mov     rcx, [rbx+80h]; pv
0x18016edca  mov     [rbx+78h], rdi
0x18016edce  call    cs:__imp_CoTaskMemFree
0x18016edd4  mov     rcx, [rbx+88h]; pv
0x18016eddb  mov     [rbx+80h], rdi
0x18016ede2  call    cs:__imp_CoTaskMemFree
0x18016ede8  mov     [rbx+88h], rdi
0x18016edef  xor     eax, eax
0x18016edf1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016edf8  movdqu  xmmword ptr [rbx+90h], xmm0
0x18016ee00  mov     [rbx+0A0h], rax
0x18016ee07  mov     rbx, [rsp+28h+arg_0]
0x18016ee0c  add     rsp, 20h
0x18016ee10  pop     rdi
0x18016ee11  retn
```
