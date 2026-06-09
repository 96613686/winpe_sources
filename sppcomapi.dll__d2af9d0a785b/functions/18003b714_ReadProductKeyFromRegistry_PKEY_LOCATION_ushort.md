# ReadProductKeyFromRegistry(PKEY_LOCATION,ushort * *)

- ea: `0x18003b714`
- end: `0x18003b870`
- name: `?ReadProductKeyFromRegistry@@YAJW4PKEY_LOCATION@@PEAPEAG@Z`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005810`

## callees

- `0x180003520`
- `0x180004288`
- `0x18003af34`
- `0x18003b354`
- `0x18003b570`
- `0x18003b714`
- `0x18003bd80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b79b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b7b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b7b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7cc`

## pseudocode

```c
__int64 __fastcall ReadProductKeyFromRegistry(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  int Value; // eax
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  HKEY v14; // [rsp+20h] [rbp-10h]
  DWORD v15; // [rsp+58h] [rbp+28h] BYREF
  __int64 v16; // [rsp+60h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+38h] BYREF

  hMem = 0;
  v16 = 0;
  if ( !a2 )
    goto LABEL_2;
  v15 = 0;
  if ( !(_DWORD)a1 )
  {
    v10 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\DefaultProductKey";
LABEL_17:
    Value = CRegUtilT<void *,CRegType,0,1>::GetValue(a1, v10, L"DigitalProductId", (BYTE **)&hMem, &v15);
    v5 = Value;
    if ( Value < 0 )
      goto LABEL_9;
    if ( v15 != 164 || *(_DWORD *)hMem != 164 )
    {
      v4 = 2147549183LL;
      goto LABEL_3;
    }
    if ( hMem == (HLOCAL)-52LL )
    {
      v12 = 2147942487LL;
      v5 = -2147024809;
    }
    else
    {
      v13 = CProductKeyUtilsT<CEmptyType>::BinaryDecode((char *)hMem + 52, v11, &v16);
      v5 = v13;
      if ( v13 >= 0 )
        goto LABEL_27;
      v12 = (unsigned int)v13;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
LABEL_27:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
    if ( (v5 & 0x80000000) != 0 )
    {
      v4 = v5;
      goto LABEL_10;
    }
    goto LABEL_8;
  }
  a1 = (unsigned int)(a1 - 1);
  if ( !(_DWORD)a1 )
  {
    v10 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\";
    goto LABEL_17;
  }
  if ( (_DWORD)a1 == 1 )
  {
    Value = CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(1, a2, a3, (int)&v16, v14);
    v5 = Value;
    if ( Value >= 0 )
    {
LABEL_8:
      Value = CMiscHelpersT<CEmptyType>::AssignString(v16, a2, 0x7FFFFFFF);
      v5 = Value;
      if ( Value >= 0 )
        goto LABEL_11;
    }
LABEL_9:
    v4 = (unsigned int)Value;
    goto LABEL_10;
  }
LABEL_2:
  v4 = 2147942487LL;
LABEL_3:
  v5 = v4;
LABEL_10:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  v7 = v16;
  if ( v16 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( hMem )
    LocalFree(hMem);
  return v5;
}

```

## disassembly

```asm
0x18003b714  push    rbp
0x18003b716  push    rbx
0x18003b717  push    rdi
0x18003b718  mov     rbp, rsp
0x18003b71b  sub     rsp, 30h
0x18003b71f  mov     [rbp+hMem], 0
0x18003b727  mov     rbx, rdx
0x18003b72a  mov     [rbp+arg_10], 0
0x18003b732  test    rdx, rdx
0x18003b735  jnz     short loc_18003B740
0x18003b737  mov     ecx, 80070057h
0x18003b73c  mov     edi, ecx
0x18003b73e  jmp     short loc_18003B786
0x18003b740  mov     [rbp+arg_8], 0
0x18003b747  test    ecx, ecx
0x18003b749  jz      loc_18003B821
0x18003b74f  sub     ecx, 1; int
0x18003b752  jz      loc_18003B7E3
0x18003b758  cmp     ecx, 1
0x18003b75b  jnz     short loc_18003B737
0x18003b75d  lea     r9, [rbp+arg_10]; int
0x18003b761  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x18003b766  mov     edi, eax
0x18003b768  test    eax, eax
0x18003b76a  js      short loc_18003B784
0x18003b76c  mov     rcx, [rbp+arg_10]
0x18003b770  mov     r8d, 7FFFFFFFh
0x18003b776  mov     rdx, rbx
0x18003b779  call    ?AssignString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAGI@Z; CMiscHelpersT<CEmptyType>::AssignString(ushort const *,ushort * *,uint)
0x18003b77e  mov     edi, eax
0x18003b780  test    eax, eax
0x18003b782  jns     short loc_18003B78B
0x18003b784  mov     ecx, eax
0x18003b786  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b78b  mov     ecx, edi
0x18003b78d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b792  mov     rbx, [rbp+arg_10]
0x18003b796  test    rbx, rbx
0x18003b799  jz      short loc_18003B7C3
0x18003b79b  call    cs:__imp_GetProcessHeap
0x18003b7a2  nop     dword ptr [rax+rax+00h]
0x18003b7a7  lea     r8, [rbx-4]; lpMem
0x18003b7ab  xor     edx, edx; dwFlags
0x18003b7ad  mov     rcx, rax; hHeap
0x18003b7b0  call    cs:__imp_HeapFree
0x18003b7b7  nop     dword ptr [rax+rax+00h]
0x18003b7bc  xor     ecx, ecx
0x18003b7be  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b7c3  mov     rcx, [rbp+hMem]; hMem
0x18003b7c7  test    rcx, rcx
0x18003b7ca  jz      short loc_18003B7D8
0x18003b7cc  call    cs:__imp_LocalFree
0x18003b7d3  nop     dword ptr [rax+rax+00h]
0x18003b7d8  mov     eax, edi
0x18003b7da  add     rsp, 30h
0x18003b7de  pop     rdi
0x18003b7df  pop     rbx
0x18003b7e0  pop     rbp
0x18003b7e1  retn
0x18003b7e3  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003b7ea  lea     rax, [rbp+arg_8]
0x18003b7ee  lea     r9, [rbp+hMem]
0x18003b7f2  mov     [rsp+30h+var_10], rax
0x18003b7f7  lea     r8, aDigitalproduct_0; "DigitalProductId"
0x18003b7fe  call    ?GetValue@?$CRegUtilT@PEAXUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAXPEAK@Z; CRegUtilT<void *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,void * *,ulong *)
0x18003b803  mov     edi, eax
0x18003b805  test    eax, eax
0x18003b807  js      loc_18003B784
0x18003b80d  mov     ecx, 0A4h
0x18003b812  cmp     [rbp+arg_8], ecx
0x18003b815  jz      short loc_18003B82A
0x18003b817  mov     ecx, 8000FFFFh
0x18003b81c  jmp     loc_18003B73C
0x18003b821  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003b828  jmp     short loc_18003B7EA
0x18003b82a  mov     rax, [rbp+hMem]
0x18003b82e  cmp     [rax], ecx
0x18003b830  jnz     short loc_18003B817
0x18003b832  lea     rcx, [rax+34h]
0x18003b836  test    rcx, rcx
0x18003b839  jnz     short loc_18003B844
0x18003b83b  mov     ecx, 80070057h
0x18003b840  mov     edi, ecx
0x18003b842  jmp     short loc_18003B855
0x18003b844  lea     r8, [rbp+arg_10]
0x18003b848  call    ?BinaryDecode@?$CProductKeyUtilsT@VCEmptyType@@@@SAJPEBEKPEAPEAGPEAH@Z; CProductKeyUtilsT<CEmptyType>::BinaryDecode(uchar const *,ulong,ushort * *,int *)
0x18003b84d  mov     edi, eax
0x18003b84f  test    eax, eax
0x18003b851  jns     short loc_18003B85A
0x18003b853  mov     ecx, eax
0x18003b855  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b85a  mov     ecx, edi
0x18003b85c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b861  test    edi, edi
0x18003b863  jns     loc_18003B76C
0x18003b869  mov     ecx, edi
0x18003b86b  jmp     loc_18003B786
```
