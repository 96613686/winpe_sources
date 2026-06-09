# EapControls::GetDeviceAlgoCaps(void)

- ea: `0x18000d9ac`
- end: `0x18000dabf`
- name: `?GetDeviceAlgoCaps@EapControls@@QEAAKXZ`
- size: `275`
- prototype: `unsigned int __fastcall(EapControls *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008944`

## callees

- `0x18000d9ac`

## import_xrefs

- `wwapi!WwanCloseHandle` at `0x18000daaf`
- `wwapi!WwanCloseHandle` at `0x18000daaf`
- `wwapi!WwanFreeMemory` at `0x18000da80`
- `wwapi!WwanFreeMemory` at `0x18000da9e`
- `wwapi!WwanFreeMemory` at `0x18000da80`
- `wwapi!WwanFreeMemory` at `0x18000da9e`
- `wwapi!WwanEnumerateInterfaces` at `0x18000d9f5`
- `wwapi!WwanEnumerateInterfaces` at `0x18000d9f5`
- `wwapi!WwanOpenHandle` at `0x18000d9dd`
- `wwapi!WwanOpenHandle` at `0x18000d9dd`
- `wwapi!WwanQueryInterface` at `0x18000da5f`
- `wwapi!WwanQueryInterface` at `0x18000da5f`

## pseudocode

```c
__int64 __fastcall EapControls::GetDeviceAlgoCaps(EapControls *this)
{
  unsigned int *v1; // rdx
  unsigned int i; // ebx
  int v4; // [rsp+70h] [rbp+20h] BYREF
  int v5; // [rsp+74h] [rbp+24h]
  int v6; // [rsp+78h] [rbp+28h]
  unsigned int *v7; // [rsp+80h] [rbp+30h] BYREF
  __int64 v8; // [rsp+88h] [rbp+38h] BYREF

  v5 = HIDWORD(this);
  v8 = 0;
  v7 = 0;
  v4 = 0;
  if ( (unsigned int)WwanOpenHandle(1, 0, &v4, &v8) || (unsigned int)WwanEnumerateInterfaces(v8, 0, &v7) )
  {
    v1 = v7;
  }
  else
  {
    v1 = v7;
    for ( i = 0; i < *v7; ++i )
    {
      v6 = 0;
      WwanQueryInterface(v8, &v1[147 * i + 1], 7);
      v1 = v7;
    }
  }
  if ( v1 )
    WwanFreeMemory(v1);
  if ( v8 )
    WwanCloseHandle(v8, 0);
  return 0;
}

```

## disassembly

```asm
0x18000d9ac  mov     [rsp-18h+arg_0], rcx
0x18000d9b1  push    rbp
0x18000d9b2  push    rbx
0x18000d9b3  push    rdi
0x18000d9b4  mov     rbp, rsp
0x18000d9b7  sub     rsp, 50h
0x18000d9bb  xor     edi, edi
0x18000d9bd  mov     [rbp+arg_18], 0
0x18000d9c5  lea     r9, [rbp+arg_18]
0x18000d9c9  mov     [rbp+arg_10], 0
0x18000d9d1  lea     r8, [rbp+arg_0]
0x18000d9d5  mov     dword ptr [rbp+arg_0], edi
0x18000d9d8  xor     edx, edx
0x18000d9da  lea     ecx, [rdi+1]
0x18000d9dd  call    cs:__imp_WwanOpenHandle
0x18000d9e3  test    eax, eax
0x18000d9e5  jnz     loc_18000DA92
0x18000d9eb  mov     rcx, [rbp+arg_18]
0x18000d9ef  lea     r8, [rbp+arg_10]
0x18000d9f3  xor     edx, edx
0x18000d9f5  call    cs:__imp_WwanEnumerateInterfaces
0x18000d9fb  test    eax, eax
0x18000d9fd  jnz     loc_18000DA92
0x18000da03  mov     rdx, [rbp+arg_10]
0x18000da07  xor     ebx, ebx
0x18000da09  cmp     [rdx], ebx
0x18000da0b  jbe     loc_18000DA96
0x18000da11  mov     [rsp+50h+var_18], 0
0x18000da1a  xor     r9d, r9d
0x18000da1d  mov     eax, ebx
0x18000da1f  imul    rcx, rax, 24Ch
0x18000da26  lea     rax, [rbp+var_10]
0x18000da2a  mov     [rsp+50h+var_20], 0
0x18000da33  add     rcx, 4
0x18000da37  mov     [rsp+50h+var_28], rax
0x18000da3c  add     rdx, rcx
0x18000da3f  mov     [rbp+var_10], 0
0x18000da47  mov     rcx, [rbp+arg_18]
0x18000da4b  lea     rax, [rbp+arg_8]
0x18000da4f  lea     r8d, [r9+7]
0x18000da53  mov     [rbp+arg_8], 0
0x18000da5a  mov     [rsp+50h+var_30], rax
0x18000da5f  call    cs:__imp_WwanQueryInterface
0x18000da65  test    eax, eax
0x18000da67  jnz     short loc_18000DA86
0x18000da69  mov     rcx, [rbp+var_10]
0x18000da6d  test    rcx, rcx
0x18000da70  jz      short loc_18000DA86
0x18000da72  cmp     [rcx+388h], eax
0x18000da78  jnz     short loc_18000DA80
0x18000da7a  or      edi, [rcx+374h]
0x18000da80  call    cs:__imp_WwanFreeMemory
0x18000da86  mov     rdx, [rbp+arg_10]
0x18000da8a  inc     ebx
0x18000da8c  cmp     ebx, [rdx]
0x18000da8e  jb      short loc_18000DA11
0x18000da90  jmp     short loc_18000DA96
0x18000da92  mov     rdx, [rbp+arg_10]
0x18000da96  test    rdx, rdx
0x18000da99  jz      short loc_18000DAA4
0x18000da9b  mov     rcx, rdx
0x18000da9e  call    cs:__imp_WwanFreeMemory
0x18000daa4  mov     rcx, [rbp+arg_18]
0x18000daa8  test    rcx, rcx
0x18000daab  jz      short loc_18000DAB5
0x18000daad  xor     edx, edx
0x18000daaf  call    cs:__imp_WwanCloseHandle
0x18000dab5  mov     eax, edi
0x18000dab7  add     rsp, 50h
0x18000dabb  pop     rdi
0x18000dabc  pop     rbx
0x18000dabd  pop     rbp
0x18000dabe  retn
```
