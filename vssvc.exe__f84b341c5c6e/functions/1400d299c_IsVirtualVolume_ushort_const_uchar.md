# IsVirtualVolume(ushort const *,uchar *)

- ea: `0x1400d299c`
- end: `0x1400d2b77`
- name: `?IsVirtualVolume@@YAHPEBGPEAE@Z`
- size: `475`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140025e3c`

## callees

- `0x140021ca0`
- `0x140021f14`
- `0x1400227a0`
- `0x1400235a8`
- `0x1400d257c`
- `0x1400d299c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d2b5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d2b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d2b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d2b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d2b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d2b48`

## pseudocode

```c
__int64 __fastcall IsVirtualVolume(const unsigned __int16 *a1, bool *a2)
{
  WCHAR *v4; // rbx
  int v5; // r9d
  unsigned int v6; // edi
  DWORD LastError; // esi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v8; // rcx
  int v9; // edx
  const char *v10; // rax
  const WCHAR *v11; // rax
  __int64 v12; // rcx
  DWORD v13; // eax
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  TraceFunctionEnter(L"IsVirtualVolume");
  pv = 0;
  v4 = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      *a2 = 0;
      v11 = SafeStrClone(a1);
      v4 = (WCHAR *)v11;
      if ( v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        if ( v12 && v11[v12 - 1] == 92 )
          v11[v12 - 1] = 0;
        v6 = 1;
        if ( (unsigned int)AsrVhd::GetDeviceDependencyInformation(
                             v11,
                             1,
                             STORAGE_DEPENDENCY_INFO_VERSION_1,
                             (struct _STORAGE_DEPENDENCY_INFO **)&pv) )
        {
          LastError = 0;
          *a2 = pv != 0;
        }
        else
        {
          v6 = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v13 = GetLastError();
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              16,
              (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
              v13,
              "AsrVhd::GetDeviceDependencyInformation( wszVolumeNameWithoutTrailingSlash, TRUE, STORAGE_DEPENDENCY_INFO_V"
              "ERSION_1, &pVhdInfo )");
          }
        }
      }
      else
      {
        v6 = 0;
        LastError = 14;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v9 = 15;
          v5 = 14;
          v10 = "wszVolumeNameWithoutTrailingSlash";
          goto LABEL_5;
        }
      }
    }
    else
    {
      v5 = 87;
      v6 = 0;
      LastError = 87;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v9 = 14;
        v10 = "wszVolume";
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = 87;
    v6 = 0;
    LastError = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v9 = 13;
      v10 = "pbVirtual";
LABEL_5:
      WPP_SF_Ds(
        *(_QWORD *)v8->Gpt.DiskId.Data4,
        v9,
        (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
        v5,
        v10);
    }
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v4);
  TraceFunctionExit(L"IsVirtualVolume");
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x1400d299c  mov     [rsp+arg_0], rbx
0x1400d29a1  mov     [rsp+arg_10], rbp
0x1400d29a6  push    rsi
0x1400d29a7  push    rdi
0x1400d29a8  push    r14
0x1400d29aa  sub     rsp, 30h
0x1400d29ae  mov     r14, rdx
0x1400d29b1  mov     rdi, rcx
0x1400d29b4  lea     rcx, aIsvirtualvolum; "IsVirtualVolume"
0x1400d29bb  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d29c0  xor     ebp, ebp
0x1400d29c2  mov     [rsp+48h+pv], rbp
0x1400d29c7  mov     ebx, ebp
0x1400d29c9  test    r14, r14
0x1400d29cc  jnz     short loc_1400D2A1C
0x1400d29ce  lea     r9d, [rbp+57h]
0x1400d29d2  mov     edi, ebp
0x1400d29d4  mov     esi, r9d
0x1400d29d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d29de  lea     rax, WPP_GLOBAL_Control
0x1400d29e5  cmp     rcx, rax
0x1400d29e8  jz      loc_1400D2B3A
0x1400d29ee  test    byte ptr [rcx+1Ch], 8
0x1400d29f2  jz      loc_1400D2B3A
0x1400d29f8  lea     edx, [rbp+0Dh]
0x1400d29fb  lea     rax, aPbvirtual; "pbVirtual"
0x1400d2a02  mov     [rsp+48h+var_28], rax
0x1400d2a07  mov     rcx, [rcx+10h]
0x1400d2a0b  lea     r8, WPP_9804a34647793532e49666254d335394_Traceguids
0x1400d2a12  call    WPP_SF_Ds
0x1400d2a17  jmp     loc_1400D2B3A
0x1400d2a1c  test    rdi, rdi
0x1400d2a1f  jnz     short loc_1400D2A5A
0x1400d2a21  mov     r9d, 57h ; 'W'
0x1400d2a27  mov     edi, ebp
0x1400d2a29  mov     esi, r9d
0x1400d2a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2a33  lea     rax, WPP_GLOBAL_Control
0x1400d2a3a  cmp     rcx, rax
0x1400d2a3d  jz      loc_1400D2B3A
0x1400d2a43  test    byte ptr [rcx+1Ch], 8
0x1400d2a47  jz      loc_1400D2B3A
0x1400d2a4d  lea     edx, [r9-49h]
0x1400d2a51  lea     rax, aWszvolume; "wszVolume"
0x1400d2a58  jmp     short loc_1400D2A02
0x1400d2a5a  mov     rcx, rdi; unsigned __int16 *
0x1400d2a5d  mov     [r14], bpl
0x1400d2a60  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x1400d2a65  mov     rbx, rax
0x1400d2a68  test    rax, rax
0x1400d2a6b  jnz     short loc_1400D2AA5
0x1400d2a6d  mov     edi, ebp
0x1400d2a6f  lea     esi, [rax+0Eh]
0x1400d2a72  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2a79  lea     rax, WPP_GLOBAL_Control
0x1400d2a80  cmp     rcx, rax
0x1400d2a83  jz      loc_1400D2B3A
0x1400d2a89  test    byte ptr [rcx+1Ch], 8
0x1400d2a8d  jz      loc_1400D2B3A
0x1400d2a93  lea     edx, [rbx+0Fh]
0x1400d2a96  mov     r9d, esi
0x1400d2a99  lea     rax, aWszvolumenamew; "wszVolumeNameWithoutTrailingSlash"
0x1400d2aa0  jmp     loc_1400D2A02
0x1400d2aa5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400d2aa9  inc     rcx
0x1400d2aac  cmp     [rax+rcx*2], bp
0x1400d2ab0  jnz     short loc_1400D2AA9
0x1400d2ab2  test    rcx, rcx
0x1400d2ab5  jz      short loc_1400D2AC4
0x1400d2ab7  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400d2abd  jnz     short loc_1400D2AC4
0x1400d2abf  mov     [rax+rcx*2-2], bp
0x1400d2ac4  mov     edi, 1
0x1400d2ac9  lea     r9, [rsp+48h+pv]; struct _STORAGE_DEPENDENCY_INFO **
0x1400d2ace  mov     r8d, edi; enum _STORAGE_DEPENDENCY_INFO_VERSION
0x1400d2ad1  mov     dl, dil; unsigned __int8
0x1400d2ad4  mov     rcx, rax; lpFileName
0x1400d2ad7  call    ?GetDeviceDependencyInformation@AsrVhd@@SAHPEBGEW4_STORAGE_DEPENDENCY_INFO_VERSION@@PEAPEAU_STORAGE_DEPENDENCY_INFO@@@Z; AsrVhd::GetDeviceDependencyInformation(ushort const *,uchar,_STORAGE_DEPENDENCY_INFO_VERSION,_STORAGE_DEPENDENCY_INFO * *)
0x1400d2adc  test    eax, eax
0x1400d2ade  jnz     short loc_1400D2B29
0x1400d2ae0  mov     edi, ebp
0x1400d2ae2  call    cs:__imp_GetLastError
0x1400d2ae8  mov     esi, eax
0x1400d2aea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2af1  lea     rax, WPP_GLOBAL_Control
0x1400d2af8  cmp     rcx, rax
0x1400d2afb  jz      short loc_1400D2B3A
0x1400d2afd  test    byte ptr [rcx+1Ch], 8
0x1400d2b01  jz      short loc_1400D2B3A
0x1400d2b03  call    cs:__imp_GetLastError
0x1400d2b09  lea     rcx, aAsrvhdGetdevic; "AsrVhd::GetDeviceDependencyInformation("...
0x1400d2b10  mov     edx, 10h
0x1400d2b15  mov     [rsp+48h+var_28], rcx
0x1400d2b1a  mov     r9d, eax
0x1400d2b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2b24  jmp     loc_1400D2A07
0x1400d2b29  cmp     [rsp+48h+pv], rbp
0x1400d2b2e  mov     esi, ebp
0x1400d2b30  movzx   edx, bpl
0x1400d2b34  cmovnz  edx, edi
0x1400d2b37  mov     [r14], dl
0x1400d2b3a  mov     rcx, [rsp+48h+pv]; pv
0x1400d2b3f  call    cs:__imp_CoTaskMemFree
0x1400d2b45  mov     rcx, rbx; pv
0x1400d2b48  call    cs:__imp_CoTaskMemFree
0x1400d2b4e  lea     rcx, aIsvirtualvolum; "IsVirtualVolume"
0x1400d2b55  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d2b5a  mov     ecx, esi; dwErrCode
0x1400d2b5c  call    cs:__imp_SetLastError
0x1400d2b62  mov     rbx, [rsp+48h+arg_0]
0x1400d2b67  mov     eax, edi
0x1400d2b69  mov     rbp, [rsp+48h+arg_10]
0x1400d2b6e  add     rsp, 30h
0x1400d2b72  pop     r14
0x1400d2b74  pop     rdi
0x1400d2b75  pop     rsi
0x1400d2b76  retn
```
