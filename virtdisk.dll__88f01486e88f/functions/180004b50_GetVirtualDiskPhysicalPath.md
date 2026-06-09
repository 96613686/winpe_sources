# GetVirtualDiskPhysicalPath

- ea: `0x180004b50`
- end: `0x180004ec3`
- name: `GetVirtualDiskPhysicalPath`
- size: `883`
- prototype: `DWORD __stdcall(HANDLE VirtualDiskHandle, PULONG DiskPathSizeInBytes, PWSTR DiskPath)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004110`
- `0x180004b50`
- `0x1800063a8`
- `0x180006fac`
- `0x1800076cc`
- `0x180008834`
- `0x18000ba11`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004cbe`
- `ntdll!RtlFreeHeap` at `0x180004e47`
- `ntdll!RtlFreeHeap` at `0x180004cbe`
- `ntdll!RtlFreeHeap` at `0x180004e47`
- `ntdll!RtlAllocateHeap` at `0x180004c15`
- `ntdll!RtlAllocateHeap` at `0x180004cdf`
- `ntdll!RtlAllocateHeap` at `0x180004c15`
- `ntdll!RtlAllocateHeap` at `0x180004cdf`

## pseudocode

```c
DWORD __stdcall GetVirtualDiskPhysicalPath(HANDLE VirtualDiskHandle, PULONG DiskPathSizeInBytes, PWSTR DiskPath)
{
  _QWORD *v6; // rcx
  unsigned int NtDiskNumber; // ebx
  _DWORD *Heap; // r14
  unsigned int v9; // r15d
  DWORD v10; // eax
  DWORD v11; // ebx
  const WCHAR *v12; // rcx
  __int64 v13; // rax
  ULONG v15; // ebp
  ULONG v16; // ebx
  const wchar_t *v17; // r8
  HRESULT v18; // eax
  __int64 v20; // [rsp+40h] [rbp-48h] BYREF
  int v21; // [rsp+48h] [rbp-40h]
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF
  int InBuffer; // [rsp+A8h] [rbp+20h] BYREF

  InBuffer = 0;
  NumberOfBytesTransferred = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6afab5048b663292b11c40fad9d08467_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (char *)VirtualDiskHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    NtDiskNumber = 6;
    goto LABEL_43;
  }
  if ( DiskPathSizeInBytes )
  {
    if ( DiskPath || !*DiskPathSizeInBytes )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8u);
      if ( Heap )
      {
        v9 = 1;
        InBuffer = 1;
        v10 = IssueSynchronousDeviceIoControl(
                VirtualDiskHandle,
                0x2D1934u,
                &InBuffer,
                4u,
                Heap,
                8u,
                &NumberOfBytesTransferred);
        NtDiskNumber = v10;
        if ( v10 )
        {
          if ( v10 == 234 && NumberOfBytesTransferred >= 8 )
          {
            v11 = Heap[1] + 8 + *Heap;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
            if ( !Heap )
            {
              v6 = WPP_GLOBAL_Control;
              NtDiskNumber = 14;
              goto LABEL_43;
            }
            NtDiskNumber = IssueSynchronousDeviceIoControl(
                             VirtualDiskHandle,
                             0x2D1934u,
                             &InBuffer,
                             4u,
                             Heap,
                             v11,
                             &NumberOfBytesTransferred);
            if ( !NtDiskNumber )
            {
              v12 = (const WCHAR *)((char *)Heap + (unsigned int)*Heap);
              if ( *v12 == 92 && v12[1] == 63 && v12[2] == 63 && v12[3] == 92 )
              {
                v13 = -1;
                while ( v12[++v13] != 0 )
                  ;
                v15 = 2 * v13 + 2;
                if ( *DiskPathSizeInBytes >= v15 )
                {
                  memcpy_0(DiskPath, (char *)Heap + (unsigned int)*Heap, v15);
                  *(_DWORD *)(DiskPath + 1) = 3014748;
                  NtDiskNumber = 0;
                }
                else
                {
                  NtDiskNumber = 122;
                }
                *DiskPathSizeInBytes = v15;
              }
              else
              {
                v20 = 0;
                v21 = 0;
                NtDiskNumber = GetNtDiskNumber(v12, (__int64)&v20);
                if ( !NtDiskNumber )
                {
                  if ( (_DWORD)v20 == 7 || (v16 = 20, (_DWORD)v20 == 36) )
                    v16 = 36;
                  do
                  {
                    v9 *= 10;
                    v16 += 2;
                  }
                  while ( HIDWORD(v20) / v9 );
                  if ( *DiskPathSizeInBytes >= v16 )
                  {
                    if ( (_DWORD)v20 == 7 || (v17 = L"\\\\.\\CDROM%d", (_DWORD)v20 == 36) )
                      v17 = L"\\\\.\\PHYSICALDRIVE%d";
                    v18 = StringCbPrintfW(DiskPath, *DiskPathSizeInBytes, v17);
                    *DiskPathSizeInBytes = v16;
                    NtDiskNumber = v18 != 0 ? 0x7A : 0;
                  }
                  else
                  {
                    *DiskPathSizeInBytes = v16;
                    NtDiskNumber = 122;
                  }
                }
              }
            }
          }
        }
        else
        {
          NtDiskNumber = 87;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        v6 = WPP_GLOBAL_Control;
        goto LABEL_43;
      }
      v6 = WPP_GLOBAL_Control;
      NtDiskNumber = 14;
    }
    else
    {
      NtDiskNumber = 87;
    }
  }
  else
  {
    NtDiskNumber = 87;
  }
LABEL_43:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_d(v6[2], 15, WPP_6afab5048b663292b11c40fad9d08467_Traceguids, NtDiskNumber);
  return NtDiskNumber;
}

```

## disassembly

```asm
0x180004b50  mov     rax, rsp
0x180004b53  sub     rsp, 88h
0x180004b5a  mov     [rax-8], rbp
0x180004b5e  mov     rbp, rcx
0x180004b61  mov     [rax-10h], rsi
0x180004b65  mov     rsi, r8
0x180004b68  mov     [rax-18h], rdi
0x180004b6c  mov     rdi, rdx
0x180004b6f  mov     [rax-20h], r12
0x180004b73  mov     [rax-28h], r13
0x180004b77  xor     r13d, r13d
0x180004b7a  mov     [rax+20h], r13d
0x180004b7e  mov     [rax+8], r13d
0x180004b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b89  lea     r12, WPP_GLOBAL_Control
0x180004b90  cmp     rcx, r12
0x180004b93  jz      short loc_180004BBD
0x180004b95  test    byte ptr [rcx+1Ch], 20h
0x180004b99  jz      short loc_180004BBD
0x180004b9b  cmp     byte ptr [rcx+19h], 4
0x180004b9f  jb      short loc_180004BBD
0x180004ba1  mov     rcx, [rcx+10h]
0x180004ba5  lea     r8, WPP_6afab5048b663292b11c40fad9d08467_Traceguids
0x180004bac  mov     edx, 0Eh
0x180004bb1  call    WPP_SF_
0x180004bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bbd  mov     [rsp+88h+arg_8], rbx
0x180004bc5  lea     rax, [rbp-1]
0x180004bc9  mov     [rsp+88h+var_30], r14
0x180004bce  mov     [rsp+88h+var_38], r15
0x180004bd3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004bd7  ja      loc_180004E5C
0x180004bdd  test    rdi, rdi
0x180004be0  jnz     short loc_180004BEC
0x180004be2  mov     ebx, 57h ; 'W'
0x180004be7  jmp     loc_180004E61
0x180004bec  test    rsi, rsi
0x180004bef  jnz     short loc_180004C00
0x180004bf1  cmp     [rdi], r13d
0x180004bf4  jz      short loc_180004C00
0x180004bf6  mov     ebx, 57h ; 'W'
0x180004bfb  jmp     loc_180004E61
0x180004c00  mov     rcx, gs:60h
0x180004c09  mov     edx, 8; Flags
0x180004c0e  mov     r8d, edx; Size
0x180004c11  mov     rcx, [rcx+30h]; HeapHandle
0x180004c15  call    cs:__imp_RtlAllocateHeap
0x180004c1c  nop     dword ptr [rax+rax+00h]
0x180004c21  mov     r14, rax
0x180004c24  test    rax, rax
0x180004c27  jnz     short loc_180004C3A
0x180004c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c30  mov     ebx, 0Eh
0x180004c35  jmp     loc_180004E61
0x180004c3a  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x180004c42  mov     r15d, 1
0x180004c48  mov     [rsp+88h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180004c4d  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x180004c55  mov     [rsp+88h+var_60], 8; DWORD
0x180004c5d  mov     r9d, 4; nInBufferSize
0x180004c63  mov     edx, 2D1934h; dwIoControlCode
0x180004c68  mov     [rsp+88h+var_68], r14; LPVOID
0x180004c6d  mov     rcx, rbp; hFile
0x180004c70  mov     [rsp+88h+InBuffer], r15d
0x180004c78  call    IssueSynchronousDeviceIoControl
0x180004c7d  mov     ebx, eax
0x180004c7f  test    eax, eax
0x180004c81  jz      loc_180004E30
0x180004c87  cmp     eax, 0EAh
0x180004c8c  jnz     loc_180004E35
0x180004c92  cmp     [rsp+88h+NumberOfBytesTransferred], 8
0x180004c9a  jb      loc_180004E35
0x180004ca0  mov     ecx, [r14+4]
0x180004ca4  mov     r8, r14; P
0x180004ca7  mov     ebx, [r14]
0x180004caa  add     ecx, 8
0x180004cad  add     ebx, ecx
0x180004caf  xor     edx, edx; Flags
0x180004cb1  mov     rcx, gs:60h
0x180004cba  mov     rcx, [rcx+30h]; HeapHandle
0x180004cbe  call    cs:__imp_RtlFreeHeap
0x180004cc5  nop     dword ptr [rax+rax+00h]
0x180004cca  mov     rcx, gs:60h
0x180004cd3  mov     edx, 8; Flags
0x180004cd8  mov     r8d, ebx; Size
0x180004cdb  mov     rcx, [rcx+30h]; HeapHandle
0x180004cdf  call    cs:__imp_RtlAllocateHeap
0x180004ce6  nop     dword ptr [rax+rax+00h]
0x180004ceb  mov     r14, rax
0x180004cee  test    rax, rax
0x180004cf1  jnz     short loc_180004D04
0x180004cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cfa  mov     ebx, 0Eh
0x180004cff  jmp     loc_180004E61
0x180004d04  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x180004d0c  mov     r9d, 4; nInBufferSize
0x180004d12  mov     [rsp+88h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180004d17  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x180004d1f  mov     [rsp+88h+var_60], ebx; DWORD
0x180004d23  mov     edx, 2D1934h; dwIoControlCode
0x180004d28  mov     rcx, rbp; hFile
0x180004d2b  mov     [rsp+88h+var_68], r14; LPVOID
0x180004d30  call    IssueSynchronousDeviceIoControl
0x180004d35  mov     ebx, eax
0x180004d37  test    eax, eax
0x180004d39  jnz     loc_180004E35
0x180004d3f  mov     ecx, [r14]
0x180004d42  add     rcx, r14; SourceString
0x180004d45  cmp     word ptr [rcx], 5Ch ; '\'
0x180004d49  jnz     short loc_180004DA4
0x180004d4b  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180004d50  jnz     short loc_180004DA4
0x180004d52  cmp     word ptr [rcx+4], 3Fh ; '?'
0x180004d57  jnz     short loc_180004DA4
0x180004d59  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180004d5e  jnz     short loc_180004DA4
0x180004d60  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004d67  cmp     [rcx+rax*2+2], r13w
0x180004d6d  lea     rax, [rax+1]
0x180004d71  jnz     short loc_180004D67
0x180004d73  lea     ebp, ds:2[rax*2]
0x180004d7a  cmp     [rdi], ebp
0x180004d7c  jnb     short loc_180004D85
0x180004d7e  mov     ebx, 7Ah ; 'z'
0x180004d83  jmp     short loc_180004D9D
0x180004d85  mov     rdx, rcx; Src
0x180004d88  mov     r8d, ebp; Size
0x180004d8b  mov     rcx, rsi; void *
0x180004d8e  call    memcpy_0
0x180004d93  mov     dword ptr [rsi+2], 2E005Ch
0x180004d9a  mov     ebx, r13d
0x180004d9d  mov     [rdi], ebp
0x180004d9f  jmp     loc_180004E35
0x180004da4  xor     eax, eax
0x180004da6  lea     rdx, [rsp+88h+var_48]
0x180004dab  mov     [rsp+88h+var_48], rax
0x180004db0  mov     [rsp+88h+var_40], eax
0x180004db4  call    GetNtDiskNumber
0x180004db9  mov     ebx, eax
0x180004dbb  test    eax, eax
0x180004dbd  jnz     short loc_180004E35
0x180004dbf  mov     ecx, dword ptr [rsp+88h+var_48]
0x180004dc3  cmp     ecx, 7
0x180004dc6  jz      short loc_180004DD2
0x180004dc8  mov     ebx, 14h
0x180004dcd  cmp     ecx, 24h ; '$'
0x180004dd0  jnz     short loc_180004DD7
0x180004dd2  mov     ebx, 24h ; '$'
0x180004dd7  mov     r9d, dword ptr [rsp+88h+var_48+4]
0x180004ddc  xor     edx, edx
0x180004dde  lea     r15d, [r15+r15*4]
0x180004de2  add     r15d, r15d
0x180004de5  mov     eax, r9d
0x180004de8  div     r15d
0x180004deb  add     ebx, 2
0x180004dee  cmp     eax, 1
0x180004df1  jnb     short loc_180004DDC
0x180004df3  mov     eax, [rdi]
0x180004df5  cmp     eax, ebx
0x180004df7  jnb     short loc_180004E02
0x180004df9  mov     [rdi], ebx
0x180004dfb  mov     ebx, 7Ah ; 'z'
0x180004e00  jmp     short loc_180004E35
0x180004e02  cmp     ecx, 7
0x180004e05  jz      short loc_180004E13
0x180004e07  lea     r8, aCdromD; "\\\\.\\CDROM%d"
0x180004e0e  cmp     ecx, 24h ; '$'
0x180004e11  jnz     short loc_180004E1A
0x180004e13  lea     r8, aPhysicaldriveD; "\\\\.\\PHYSICALDRIVE%d"
0x180004e1a  mov     rdx, rax; cbDest
0x180004e1d  mov     rcx, rsi; pszDest
0x180004e20  call    StringCbPrintfW
0x180004e25  neg     eax
0x180004e27  mov     [rdi], ebx
0x180004e29  sbb     ebx, ebx
0x180004e2b  and     ebx, 7Ah
0x180004e2e  jmp     short loc_180004E35
0x180004e30  mov     ebx, 57h ; 'W'
0x180004e35  mov     rcx, gs:60h
0x180004e3e  mov     r8, r14; P
0x180004e41  xor     edx, edx; Flags
0x180004e43  mov     rcx, [rcx+30h]; HeapHandle
0x180004e47  call    cs:__imp_RtlFreeHeap
0x180004e4e  nop     dword ptr [rax+rax+00h]
0x180004e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e5a  jmp     short loc_180004E61
0x180004e5c  mov     ebx, 6
0x180004e61  mov     r15, [rsp+88h+var_38]
0x180004e66  cmp     rcx, r12
0x180004e69  mov     r12, [rsp+88h+var_20]
0x180004e6e  mov     r14, [rsp+88h+var_30]
0x180004e73  mov     r13, [rsp+88h+var_28]
0x180004e78  mov     rdi, [rsp+88h+var_18]
0x180004e7d  mov     rsi, [rsp+88h+var_10]
0x180004e82  mov     rbp, [rsp+88h+var_8]
0x180004e8a  jz      short loc_180004EB0
0x180004e8c  test    byte ptr [rcx+1Ch], 20h
0x180004e90  jz      short loc_180004EB0
0x180004e92  cmp     byte ptr [rcx+19h], 4
0x180004e96  jb      short loc_180004EB0
0x180004e98  mov     rcx, [rcx+10h]
0x180004e9c  lea     r8, WPP_6afab5048b663292b11c40fad9d08467_Traceguids
0x180004ea3  mov     edx, 0Fh
0x180004ea8  mov     r9d, ebx
0x180004eab  call    WPP_SF_d
0x180004eb0  mov     eax, ebx
0x180004eb2  mov     rbx, [rsp+88h+arg_8]
0x180004eba  add     rsp, 88h
0x180004ec1  retn
```
