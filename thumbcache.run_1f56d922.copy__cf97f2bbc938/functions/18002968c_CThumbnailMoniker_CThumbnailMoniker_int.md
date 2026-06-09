# CThumbnailMoniker::CThumbnailMoniker(int)

- ea: `0x18002968c`
- end: `0x1800296c7`
- name: `??0CThumbnailMoniker@@QEAA@H@Z`
- size: `59`
- prototype: `CThumbnailMoniker *__fastcall(CThumbnailMoniker *__hidden this, int)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040cd0`
- `0x180041040`
- `0x1800415a0`
- `0x1800435b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800296a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800296a9`

## pseudocode

```c
CThumbnailMoniker *__fastcall CThumbnailMoniker::CThumbnailMoniker(CThumbnailMoniker *this, int a2)
{
  CThumbnailMoniker *result; // rax

  *((_DWORD *)this + 6) = a2;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  CoTaskMemFree(0);
  result = this;
  *((_DWORD *)this + 7) = 0;
  *((_QWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x18002968c  push    rbx
0x18002968e  sub     rsp, 20h
0x180029692  mov     [rcx+18h], edx
0x180029695  mov     rbx, rcx
0x180029698  mov     qword ptr [rcx], 0
0x18002969f  mov     qword ptr [rcx+10h], 0
0x1800296a7  xor     ecx, ecx; pv
0x1800296a9  call    cs:__imp_CoTaskMemFree
0x1800296af  mov     rax, rbx
0x1800296b2  mov     dword ptr [rbx+1Ch], 0
0x1800296b9  mov     qword ptr [rbx+8], 0
0x1800296c1  add     rsp, 20h
0x1800296c5  pop     rbx
0x1800296c6  retn
```
