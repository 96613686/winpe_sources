# DocEventContainer2Buffer(int,int,_DOCUMENT_EVENT_CONTAINER *,_DOCEVENT_CREATEDCPRE *,_DOCINFOW *,ulong *,uchar * *,PrintPropertiesCollection *)

- ea: `0x14000d17c`
- end: `0x14000d25c`
- name: `?DocEventContainer2Buffer@@YAKHHPEAU_DOCUMENT_EVENT_CONTAINER@@PEAU_DOCEVENT_CREATEDCPRE@@PEAU_DOCINFOW@@PEAKPEAPEAEPEAUPrintPropertiesCollection@@@Z`
- size: `224`
- prototype: `unsigned int(int, int, struct _DOCUMENT_EVENT_CONTAINER *, struct _DOCEVENT_CREATEDCPRE *, struct _DOCINFOW *, unsigned int *, unsigned __int8 **, struct PrintPropertiesCollection *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d9e0`

## callees

- `0x14000d17c`
- `0x14000d264`

## pseudocode

```c
__int64 __fastcall DocEventContainer2Buffer(
        int a1,
        int a2,
        struct _DOCUMENT_EVENT_CONTAINER *a3,
        struct _DOCEVENT_CREATEDCPRE *a4,
        struct _DOCINFOW *a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        struct PrintPropertiesCollection *a8)
{
  unsigned int v9; // edx

  if ( a1 )
  {
    v9 = XpsContainer2PrintProperties(a2, a3, a8);
    if ( !v9 )
    {
      *a6 = 0;
      *a7 = (unsigned __int8 *)a8;
    }
  }
  else
  {
    v9 = 0;
    if ( a2 == 1 || a2 == 14 )
    {
      a4->pszDriver = (PWSTR)*((_QWORD *)a3 + 1);
      a4->pszDevice = (PWSTR)*((_QWORD *)a3 + 2);
      a4->bIC = *((_DWORD *)a3 + 10);
      a4->pdm = (PDEVMODEW)*((_QWORD *)a3 + 4);
      *a7 = (unsigned __int8 *)a4;
      *a6 = 32;
    }
    else if ( a2 == 5 )
    {
      a5->cbSize = 40;
      a5->lpszDocName = (LPCWSTR)*((_QWORD *)a3 + 1);
      a5->lpszOutput = (LPCWSTR)*((_QWORD *)a3 + 2);
      a5->lpszDatatype = (LPCWSTR)*((_QWORD *)a3 + 3);
      a5->fwType = *((_DWORD *)a3 + 8);
      *a7 = (unsigned __int8 *)a5;
      *a6 = 40;
    }
    else
    {
      *a6 = *((_DWORD *)a3 + 2);
      *a7 = (unsigned __int8 *)*((_QWORD *)a3 + 2);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14000d17c  push    rbx
0x14000d17e  sub     rsp, 20h
0x14000d182  mov     r10, r8
0x14000d185  mov     eax, edx
0x14000d187  test    ecx, ecx
0x14000d189  jz      short loc_14000D1BB
0x14000d18b  mov     rbx, [rsp+28h+arg_38]
0x14000d190  mov     rdx, r10; struct _DOCUMENT_EVENT_CONTAINER *
0x14000d193  mov     r8, rbx; struct PrintPropertiesCollection *
0x14000d196  mov     ecx, eax; int
0x14000d198  call    ?XpsContainer2PrintProperties@@YAKHPEAU_DOCUMENT_EVENT_CONTAINER@@PEAUPrintPropertiesCollection@@@Z; XpsContainer2PrintProperties(int,_DOCUMENT_EVENT_CONTAINER *,PrintPropertiesCollection *)
0x14000d19d  mov     edx, eax
0x14000d19f  test    eax, eax
0x14000d1a1  jnz     loc_14000D254
0x14000d1a7  mov     rcx, [rsp+28h+arg_28]
0x14000d1ac  mov     [rcx], eax
0x14000d1ae  mov     rcx, [rsp+28h+arg_30]
0x14000d1b3  mov     [rcx], rbx
0x14000d1b6  jmp     loc_14000D254
0x14000d1bb  xor     edx, edx
0x14000d1bd  cmp     eax, 1
0x14000d1c0  jz      short loc_14000D222
0x14000d1c2  cmp     eax, 0Eh
0x14000d1c5  jz      short loc_14000D222
0x14000d1c7  cmp     eax, 5
0x14000d1ca  jnz     short loc_14000D209
0x14000d1cc  mov     rcx, [rsp+28h+arg_20]
0x14000d1d1  lea     r8d, [rdx+28h]
0x14000d1d5  mov     [rcx], r8d
0x14000d1d8  mov     rax, [r10+8]
0x14000d1dc  mov     [rcx+8], rax
0x14000d1e0  mov     rax, [r10+10h]
0x14000d1e4  mov     [rcx+10h], rax
0x14000d1e8  mov     rax, [r10+18h]
0x14000d1ec  mov     [rcx+18h], rax
0x14000d1f0  mov     eax, [r10+20h]
0x14000d1f4  mov     [rcx+20h], eax
0x14000d1f7  mov     rax, [rsp+28h+arg_30]
0x14000d1fc  mov     [rax], rcx
0x14000d1ff  mov     rax, [rsp+28h+arg_28]
0x14000d204  mov     [rax], r8d
0x14000d207  jmp     short loc_14000D254
0x14000d209  mov     rax, [rsp+28h+arg_28]
0x14000d20e  mov     ecx, [r8+8]
0x14000d212  mov     [rax], ecx
0x14000d214  mov     rax, [rsp+28h+arg_30]
0x14000d219  mov     rcx, [r8+10h]
0x14000d21d  mov     [rax], rcx
0x14000d220  jmp     short loc_14000D254
0x14000d222  mov     rax, [r8+8]
0x14000d226  mov     [r9], rax
0x14000d229  mov     rax, [r8+10h]
0x14000d22d  mov     [r9+8], rax
0x14000d231  mov     eax, [r8+28h]
0x14000d235  mov     [r9+18h], eax
0x14000d239  mov     rax, [r8+20h]
0x14000d23d  mov     [r9+10h], rax
0x14000d241  mov     rax, [rsp+28h+arg_30]
0x14000d246  mov     [rax], r9
0x14000d249  mov     rax, [rsp+28h+arg_28]
0x14000d24e  mov     dword ptr [rax], 20h ; ' '
0x14000d254  mov     eax, edx
0x14000d256  add     rsp, 20h
0x14000d25a  pop     rbx
0x14000d25b  retn
```
