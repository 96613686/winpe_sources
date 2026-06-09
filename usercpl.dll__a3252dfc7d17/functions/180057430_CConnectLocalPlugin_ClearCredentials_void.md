# CConnectLocalPlugin::ClearCredentials(void)

- ea: `0x180057430`
- end: `0x1800574b8`
- name: `?ClearCredentials@CConnectLocalPlugin@@UEAAXXZ`
- size: `136`
- prototype: `void __fastcall(CConnectLocalPlugin *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800570b0`
- `0x1800574c0`

## callees

- `0x180057430`
- `0x18006e7f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057480`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005749c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057480`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005749c`

## pseudocode

```c
void __fastcall CConnectLocalPlugin::ClearCredentials(LPVOID *this)
{
  unsigned __int16 *v2; // rcx
  _BYTE *v3; // rcx
  __int64 v4; // rdx
  _BYTE *v5; // rax
  void *v6; // rcx

  CoTaskMemFree(this[13]);
  v2 = (unsigned __int16 *)this[11];
  this[13] = 0;
  ClearAndFreeSecretString(v2);
  v3 = this[14];
  this[11] = 0;
  if ( v3 )
  {
    v4 = *((unsigned int *)this + 30);
    v5 = v3;
    if ( *((_DWORD *)this + 30) )
    {
      do
      {
        *v5++ = 0;
        --v4;
      }
      while ( v4 );
    }
    CoTaskMemFree(v3);
  }
  v6 = this[16];
  this[14] = 0;
  *((_DWORD *)this + 30) = 0;
  CoTaskMemFree(v6);
  this[16] = 0;
}

```

## disassembly

```asm
0x180057430  mov     [rsp+arg_0], rbx
0x180057435  push    rdi
0x180057436  sub     rsp, 20h
0x18005743a  mov     rbx, rcx
0x18005743d  mov     rcx, [rcx+68h]; pv
0x180057441  call    cs:__imp_CoTaskMemFree
0x180057447  mov     rcx, [rbx+58h]; unsigned __int16 *
0x18005744b  mov     qword ptr [rbx+68h], 0
0x180057453  call    ?ClearAndFreeSecretString@@YAXPEAG@Z; ClearAndFreeSecretString(ushort *)
0x180057458  mov     rcx, [rbx+70h]; pv
0x18005745c  mov     qword ptr [rbx+58h], 0
0x180057464  test    rcx, rcx
0x180057467  jz      short loc_180057486
0x180057469  mov     edx, [rbx+78h]
0x18005746c  mov     rax, rcx
0x18005746f  test    rdx, rdx
0x180057472  jz      short loc_180057480
0x180057474  mov     byte ptr [rax], 0
0x180057477  inc     rax
0x18005747a  sub     rdx, 1
0x18005747e  jnz     short loc_180057474
0x180057480  call    cs:__imp_CoTaskMemFree
0x180057486  mov     rcx, [rbx+80h]; pv
0x18005748d  mov     qword ptr [rbx+70h], 0
0x180057495  mov     dword ptr [rbx+78h], 0
0x18005749c  call    cs:__imp_CoTaskMemFree
0x1800574a2  mov     qword ptr [rbx+80h], 0
0x1800574ad  mov     rbx, [rsp+28h+arg_0]
0x1800574b2  add     rsp, 20h
0x1800574b6  pop     rdi
0x1800574b7  retn
```
