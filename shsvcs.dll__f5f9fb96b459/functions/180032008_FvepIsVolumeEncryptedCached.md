# FvepIsVolumeEncryptedCached

- ea: `0x180032008`
- end: `0x1800320f4`
- name: `FvepIsVolumeEncryptedCached`
- size: `236`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800320fc`

## callees

- `0x18003196c`
- `0x180031f74`
- `0x180032008`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800320d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800320d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032096`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032096`

## string_xrefs

- `0x180032071`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FveDetect\Cache`

## pseudocode

```c
_BOOL8 __fastcall FvepIsVolumeEncryptedCached(STRSAFE_PCNZWCH pszSrc, _DWORD *a2)
{
  WCHAR *v2; // rdi
  int v5; // ebx
  LSTATUS ValueW; // eax
  HANDLE ProcessHeap; // rax
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  LPCWSTR lpValue; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  pcbData = 4;
  lpValue = 0;
  pvData = 0;
  if ( pszSrc && a2 )
  {
    *a2 = 0;
    if ( !(unsigned int)FvepIsNonDriverEncryptionStatusCachingAllowed() )
    {
      v5 = 1;
      return v5 == 0;
    }
    v5 = FvepConvertVolumeNameToCacheValueName(pszSrc, (wchar_t **)&lpValue);
    if ( v5 < 0 )
    {
      v2 = (WCHAR *)lpValue;
    }
    else
    {
      v2 = (WCHAR *)lpValue;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FveDetect\\Cache",
                 lpValue,
                 0x10u,
                 0,
                 &pvData,
                 &pcbData);
      if ( ValueW )
      {
        if ( ValueW > 0 )
          v5 = (unsigned __int16)ValueW | 0x80070000;
        else
          v5 = ValueW;
      }
      else if ( pvData )
      {
        *a2 = 1;
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180032008  push    rbx
0x18003200a  push    rsi
0x18003200b  push    rdi
0x18003200c  sub     rsp, 40h
0x180032010  xor     edi, edi
0x180032012  mov     [rsp+58h+arg_10], 4
0x18003201a  mov     [rsp+58h+lpValue], rdi
0x18003201f  mov     rsi, rdx
0x180032022  mov     [rsp+58h+arg_0], edi
0x180032026  mov     rbx, rcx
0x180032029  test    rcx, rcx
0x18003202c  jz      loc_1800320C7
0x180032032  test    rdx, rdx
0x180032035  jz      loc_1800320C7
0x18003203b  mov     [rdx], edi
0x18003203d  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x180032042  test    eax, eax
0x180032044  jnz     short loc_18003204E
0x180032046  lea     ebx, [rdi+1]
0x180032049  jmp     loc_1800320E5
0x18003204e  lea     rdx, [rsp+58h+lpValue]
0x180032053  mov     rcx, rbx; pszSrc
0x180032056  call    FvepConvertVolumeNameToCacheValueName
0x18003205b  mov     ebx, eax
0x18003205d  test    eax, eax
0x18003205f  js      short loc_1800320C0
0x180032061  lea     rax, [rsp+58h+arg_10]
0x180032066  mov     r9d, 10h; dwFlags
0x18003206c  mov     [rsp+58h+pcbData], rax; pcbData
0x180032071  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180032078  lea     rax, [rsp+58h+arg_0]
0x18003207d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180032084  mov     [rsp+58h+pvData], rax; pvData
0x180032089  mov     [rsp+58h+pdwType], rdi; pdwType
0x18003208e  mov     rdi, [rsp+58h+lpValue]
0x180032093  mov     r8, rdi; lpValue
0x180032096  call    cs:__imp_RegGetValueW
0x18003209c  test    eax, eax
0x18003209e  jz      short loc_1800320B1
0x1800320a0  jg      short loc_1800320A6
0x1800320a2  mov     ebx, eax
0x1800320a4  jmp     short loc_1800320CC
0x1800320a6  movzx   ebx, ax
0x1800320a9  or      ebx, 80070000h
0x1800320af  jmp     short loc_1800320CC
0x1800320b1  cmp     [rsp+58h+arg_0], 0
0x1800320b6  jz      short loc_1800320CC
0x1800320b8  mov     dword ptr [rsi], 1
0x1800320be  jmp     short loc_1800320CC
0x1800320c0  mov     rdi, [rsp+58h+lpValue]
0x1800320c5  jmp     short loc_1800320CC
0x1800320c7  mov     ebx, 80070057h
0x1800320cc  test    rdi, rdi
0x1800320cf  jz      short loc_1800320E5
0x1800320d1  call    cs:__imp_GetProcessHeap
0x1800320d7  mov     r8, rdi; lpMem
0x1800320da  xor     edx, edx; dwFlags
0x1800320dc  mov     rcx, rax; hHeap
0x1800320df  call    cs:__imp_HeapFree
0x1800320e5  xor     eax, eax
0x1800320e7  test    ebx, ebx
0x1800320e9  setz    al
0x1800320ec  add     rsp, 40h
0x1800320f0  pop     rdi
0x1800320f1  pop     rsi
0x1800320f2  pop     rbx
0x1800320f3  retn
```
