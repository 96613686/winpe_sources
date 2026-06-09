# CAutoplayHandler::_Cleanup(void)

- ea: `0x180180380`
- end: `0x1801804ff`
- name: `?_Cleanup@CAutoplayHandler@@AEAAXXZ`
- size: `383`
- prototype: `void __fastcall(CAutoplayHandler *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1803d5524`
- `0x1803d7510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018040b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018041f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018045b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018046f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801804ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801804c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801803f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018040b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018041f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018045b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018046f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180180497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801804ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801804c8`

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
0x180180380  mov     [rsp+arg_0], rbx
0x180180385  push    rdi
0x180180386  sub     rsp, 20h
0x18018038a  mov     rbx, rcx
0x18018038d  mov     rcx, [rcx+10h]; pv
0x180180391  call    cs:__imp_CoTaskMemFree
0x180180398  nop     dword ptr [rax+rax+00h]
0x18018039d  mov     rcx, [rbx+18h]; pv
0x1801803a1  xor     edi, edi
0x1801803a3  mov     [rbx+10h], rdi
0x1801803a7  call    cs:__imp_CoTaskMemFree
0x1801803ae  nop     dword ptr [rax+rax+00h]
0x1801803b3  mov     rcx, [rbx+20h]; pv
0x1801803b7  mov     [rbx+18h], rdi
0x1801803bb  call    cs:__imp_CoTaskMemFree
0x1801803c2  nop     dword ptr [rax+rax+00h]
0x1801803c7  mov     rcx, [rbx+28h]; pv
0x1801803cb  mov     [rbx+20h], rdi
0x1801803cf  call    cs:__imp_CoTaskMemFree
0x1801803d6  nop     dword ptr [rax+rax+00h]
0x1801803db  mov     rcx, [rbx+30h]; pv
0x1801803df  mov     [rbx+28h], rdi
0x1801803e3  call    cs:__imp_CoTaskMemFree
0x1801803ea  nop     dword ptr [rax+rax+00h]
0x1801803ef  mov     rcx, [rbx+38h]; pv
0x1801803f3  mov     [rbx+30h], rdi
0x1801803f7  call    cs:__imp_CoTaskMemFree
0x1801803fe  nop     dword ptr [rax+rax+00h]
0x180180403  mov     rcx, [rbx+40h]; pv
0x180180407  mov     [rbx+38h], rdi
0x18018040b  call    cs:__imp_CoTaskMemFree
0x180180412  nop     dword ptr [rax+rax+00h]
0x180180417  mov     rcx, [rbx+48h]; pv
0x18018041b  mov     [rbx+40h], rdi
0x18018041f  call    cs:__imp_CoTaskMemFree
0x180180426  nop     dword ptr [rax+rax+00h]
0x18018042b  mov     rcx, [rbx+50h]; pv
0x18018042f  mov     [rbx+48h], rdi
0x180180433  call    cs:__imp_CoTaskMemFree
0x18018043a  nop     dword ptr [rax+rax+00h]
0x18018043f  mov     rcx, [rbx+58h]; pv
0x180180443  mov     [rbx+50h], rdi
0x180180447  call    cs:__imp_CoTaskMemFree
0x18018044e  nop     dword ptr [rax+rax+00h]
0x180180453  mov     rcx, [rbx+60h]; pv
0x180180457  mov     [rbx+58h], rdi
0x18018045b  call    cs:__imp_CoTaskMemFree
0x180180462  nop     dword ptr [rax+rax+00h]
0x180180467  mov     rcx, [rbx+68h]; pv
0x18018046b  mov     [rbx+60h], rdi
0x18018046f  call    cs:__imp_CoTaskMemFree
0x180180476  nop     dword ptr [rax+rax+00h]
0x18018047b  mov     rcx, [rbx+70h]; pv
0x18018047f  mov     [rbx+68h], rdi
0x180180483  call    cs:__imp_CoTaskMemFree
0x18018048a  nop     dword ptr [rax+rax+00h]
0x18018048f  mov     rcx, [rbx+78h]; pv
0x180180493  mov     [rbx+70h], rdi
0x180180497  call    cs:__imp_CoTaskMemFree
0x18018049e  nop     dword ptr [rax+rax+00h]
0x1801804a3  mov     rcx, [rbx+80h]; pv
0x1801804aa  mov     [rbx+78h], rdi
0x1801804ae  call    cs:__imp_CoTaskMemFree
0x1801804b5  nop     dword ptr [rax+rax+00h]
0x1801804ba  mov     rcx, [rbx+88h]; pv
0x1801804c1  mov     [rbx+80h], rdi
0x1801804c8  call    cs:__imp_CoTaskMemFree
0x1801804cf  nop     dword ptr [rax+rax+00h]
0x1801804d4  mov     [rbx+88h], rdi
0x1801804db  xor     eax, eax
0x1801804dd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801804e4  movdqu  xmmword ptr [rbx+90h], xmm0
0x1801804ec  mov     [rbx+0A0h], rax
0x1801804f3  mov     rbx, [rsp+28h+arg_0]
0x1801804f8  add     rsp, 20h
0x1801804fc  pop     rdi
0x1801804fd  retn
```
