# SecpLoadSspiPackages(void)

- ea: `0x1800070d0`
- end: `0x1800071f5`
- name: `?SecpLoadSspiPackages@@YAJXZ`
- size: `293`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180003ee0`
- `0x1800049c0`
- `0x180005400`
- `0x180005860`
- `0x1800061a0`
- `0x180007200`
- `0x180009c90`

## callees

- `0x1800070d0`
- `0x18000d2b0`
- `0x18000d3a8`
- `0x18000d6ec`
- `0x18000edb4`
- `0x18000eeb0`
- `0x180013e40`
- `0x18001b048`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071df`

## pseudocode

```c
__int64 SecpLoadSspiPackages(void)
{
  unsigned int v0; // ebx
  PCWSTR *v2; // r14
  __int64 v3; // rdi
  struct _SECP_DLL_BINDING *Binding; // rax
  struct _LIST_ENTRY *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // [rsp+40h] [rbp+20h] BYREF
  HLOCAL v11; // [rsp+48h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+30h] BYREF

  hMem = 0;
  v11 = 0;
  v10 = 0;
  v0 = SecpReadPackageList(&v10, (unsigned __int16 ***)&v11, (BYTE **)&hMem, 0);
  if ( (v0 & 0xC0000000) == 0xC0000000 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x12u, &WPP_a2431279d589382153de9f1c7b526408_Traceguids, v0);
    return v0;
  }
  else
  {
    if ( v10 )
    {
      v2 = (PCWSTR *)v11;
      v3 = 0;
      do
      {
        Binding = (struct _SECP_DLL_BINDING *)SecpCreateBinding(v2[v3]);
        v5 = (struct _LIST_ENTRY *)Binding;
        if ( Binding )
        {
          *(_DWORD *)Binding = 0;
          LODWORD(v11) = 0;
          if ( (int)SecpIsDuplicateBinding(Binding, (int *)&v11) >= 0
            && !(_DWORD)v11
            && (unsigned int)SecpAddDll((struct _SECP_DLL_BINDING *)v5, v6, v7) )
          {
            SecpLoadSspiDll(v5, v8, v9);
          }
          SecpDerefDll((HLOCAL *)&v5->Flink);
        }
        v3 = (unsigned int)(v3 + 1);
      }
      while ( (unsigned int)v3 < v10 );
      SecPackageSspiLoaded = 1;
      if ( hMem )
        LocalFree(hMem);
      if ( v2 )
        LocalFree(v2);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800070d0  mov     [rsp-18h+arg_18], rbx
0x1800070d5  push    rbp
0x1800070d6  push    rdi
0x1800070d7  push    r14
0x1800070d9  mov     rbp, rsp
0x1800070dc  sub     rsp, 20h
0x1800070e0  xor     r9d, r9d; struct _FILETIME *
0x1800070e3  mov     [rbp+hMem], 0
0x1800070eb  lea     r8, [rbp+hMem]; void **
0x1800070ef  mov     [rbp+arg_8], 0
0x1800070f7  lea     rdx, [rbp+arg_8]; unsigned __int16 ***
0x1800070fb  mov     [rbp+arg_0], 0
0x180007102  lea     rcx, [rbp+arg_0]; unsigned int *
0x180007106  call    ?SecpReadPackageList@@YAJPEAKPEAPEAPEAGPEAPEAXPEAU_FILETIME@@@Z; SecpReadPackageList(ulong *,ushort * * *,void * *,_FILETIME *)
0x18000710b  mov     ecx, eax
0x18000710d  mov     ebx, eax
0x18000710f  mov     eax, 0C0000000h
0x180007114  and     ecx, eax
0x180007116  cmp     ecx, eax
0x180007118  jnz     short loc_180007152
0x18000711a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007121  lea     rax, WPP_GLOBAL_Control
0x180007128  cmp     rcx, rax
0x18000712b  jz      short loc_18000714B
0x18000712d  test    byte ptr [rcx+1Ch], 1
0x180007131  jz      short loc_18000714B
0x180007133  mov     rcx, [rcx+10h]
0x180007137  lea     r8, WPP_a2431279d589382153de9f1c7b526408_Traceguids
0x18000713e  mov     edx, 12h
0x180007143  mov     r9d, ebx
0x180007146  call    WPP_SF_D
0x18000714b  mov     eax, ebx
0x18000714d  jmp     loc_1800071E7
0x180007152  cmp     [rbp+arg_0], 0
0x180007156  jz      loc_1800071E5
0x18000715c  mov     r14, [rbp+arg_8]
0x180007160  xor     edi, edi
0x180007162  cmp     [rbp+arg_0], edi
0x180007165  jbe     short loc_1800071BE
0x180007167  mov     rcx, [r14+rdi*8]; SourceString
0x18000716b  call    ?SecpCreateBinding@@YAPEAU_SECP_DLL_BINDING@@PEAG@Z; SecpCreateBinding(ushort *)
0x180007170  mov     rbx, rax
0x180007173  test    rax, rax
0x180007176  jz      short loc_1800071B7
0x180007178  lea     rdx, [rbp+arg_8]; int *
0x18000717c  mov     dword ptr [rax], 0
0x180007182  mov     rcx, rax; struct _SECP_DLL_BINDING *
0x180007185  mov     dword ptr [rbp+arg_8], 0
0x18000718c  call    ?SecpIsDuplicateBinding@@YAJPEAU_SECP_DLL_BINDING@@PEAH@Z; SecpIsDuplicateBinding(_SECP_DLL_BINDING *,int *)
0x180007191  test    eax, eax
0x180007193  js      short loc_1800071AF
0x180007195  cmp     dword ptr [rbp+arg_8], 0
0x180007199  jnz     short loc_1800071AF
0x18000719b  mov     rcx, rbx; struct _SECP_DLL_BINDING *
0x18000719e  call    ?SecpAddDll@@YAHPEAU_SECP_DLL_BINDING@@@Z; SecpAddDll(_SECP_DLL_BINDING *)
0x1800071a3  test    eax, eax
0x1800071a5  jz      short loc_1800071AF
0x1800071a7  mov     rcx, rbx; struct _SECP_DLL_BINDING *
0x1800071aa  call    ?SecpLoadSspiDll@@YAJPEAU_SECP_DLL_BINDING@@@Z; SecpLoadSspiDll(_SECP_DLL_BINDING *)
0x1800071af  mov     rcx, rbx; hMem
0x1800071b2  call    ?SecpDerefDll@@YAXPEAU_SECP_DLL_BINDING@@@Z; SecpDerefDll(_SECP_DLL_BINDING *)
0x1800071b7  inc     edi
0x1800071b9  cmp     edi, [rbp+arg_0]
0x1800071bc  jb      short loc_180007167
0x1800071be  mov     rcx, [rbp+hMem]; hMem
0x1800071c2  mov     cs:?SecPackageSspiLoaded@@3HA, 1; int SecPackageSspiLoaded
0x1800071cc  test    rcx, rcx
0x1800071cf  jz      short loc_1800071D7
0x1800071d1  call    cs:__imp_LocalFree
0x1800071d7  test    r14, r14
0x1800071da  jz      short loc_1800071E5
0x1800071dc  mov     rcx, r14; hMem
0x1800071df  call    cs:__imp_LocalFree
0x1800071e5  xor     eax, eax
0x1800071e7  mov     rbx, [rsp+20h+arg_18]
0x1800071ec  add     rsp, 20h
0x1800071f0  pop     r14
0x1800071f2  pop     rdi
0x1800071f3  pop     rbp
0x1800071f4  retn
```
